#  5 Modelos

En los Modelos reside la logica de negocio (o de la aplicacion).
Equivocadamente, mucha gente cree que los modelos son solo para trabajar con
las bases de datos.

Los modelos puedes ser de muchos tipos:

  * Crear miniaturas de imagenes
  * Consumir y usar webservices
  * Crear pasarelas Scaffold de pago
  * Usar LDAP
  * Enviar mails o consultar servidores de correo
  * Interactuar con el sistema de ficheros local o via FTP, o cualquier otro protocolo
  * etc etc

##  5.1 ActiveRecord

##  5.2 Ejemplo sin ActiveRecord

##  5.3 Como usar los modelos

Los Modelos representan la logica de la aplicacion, y son parte fundamental
para el momento que se desarrolla una aplicacion, un buen uso de estos nos
proporciona un gran poder al momento que se necesita escalar, mantener y
reusar codigo en una aplicacion.

Por lo general un mal uso de los modelos es solo dejar el archivo con la
declaracion de la clase y toda la logica se genera en el controlador. Esta
practica trae como consecuencia que en primer lugar el controlador sea
dificilmente entendible por alguien que intente agregar y/o modificar algo en
esa funcionalidad, en segundo lugar lo poco que puedes rehusar el codigo en
otros controladores y lo que hace es repetirse el codigo que hace lo mismo en
otro controlador.

Partiendo de este principio los controladores NO  deberian contener ningun
tipo de logica solo se encargan de atender las peticiones del usuarios y
solicitar dicha informacion a los modelos con esto garantizamos un buen uso
del [MVC](http://www.google.com/url?q=http%3A%2F%2Fes.wikipedia.org%2Fwiki%2FM
odelo_Vista_Controlador&sa=D&sntz=1&usg=AFQjCNFo6Rn8nbUjHG5f8Qqa__2nYwMDjg) .

###  5.1 El Modelo extiende el ActiveRecord

KumbiaPHP  usa POO (Programacion orientada a objetos) , asi que ActiveRecord
es una clase que ya lleva metodos listos para usar. Estos metodos  facilitan
al usuario el manejo de las tablas de las bases de datos; entre ellos estan
los siguientes: find, find_all, save, update, etc.

El Modelo extiende la clase ActiveRecord  para que el usuario pueda añadir sus
propios metodos, y asi encapsular la logica.

###  5.2 El Modelo extiende el ActiveRecord

KumbiaPHP usa POO (Programacion orientada a objetos), asi que ActiveRecord es
una clase que ya lleva metodos listos para usar. Estos metodos facilitan al
usuario el manejo de las tablas de las bases de datos; entre ellos estan los
siguientes: find, find_all, save, update, etc.

El Modelo extiende la clase ActiveRecord para que el usuario pueda añadir sus
propios metodos, y asi encapsular la logica.

##  5.4 ActiveRecord API

A continuacion veremos una referencia de los metodos que posee la clase
ActiveRecord y su funcionalidad respectiva. Éstos se encuentran organizados
alfabeticamente:

###  5.4.1 Consultas

Metodos para hacer consulta de registros:

####  5.4.1.1 distinct ()

Este metodo ejecuta una consulta de distincion unica en la entidad, funciona
igual que un "select unique campo" viendolo desde la perspectiva del SQL. El
objetivo es devolver un array con los valores unicos del campo especificado
como parametro.

Sintaxis

distinct([string $atributo_entidad], [ "conditions: …" ], [ "order: …" ], [
"limit: …" ], [ "column: …" ])  
  
---  
  
Ejemplo

$unicos = Load:: model ( 'usuario' )-> distinct ( "estado" )  
# array('A', 'I', 'N')  
  
---  
  
Los parametros conditions, order y limit funcionan identicamente que en la
funcion find y permiten modificar la forma o los mismos valores de retorno
devueltos por esta.

####  5.4.1.2 find_all_by_sql (string $sql)

Este metodo nos permite hacer una consulta por medio de un SQL y el resultado
devuelto es un array de objetos de la misma clase con los valores de los
registros en estos. La idea es que el uso de este metodo no deberia ser comun
en nuestras aplicaciones ya que ActiveRecord se encarga de eliminar el uso del
SQL en gran porcentaje, pero hay momentos en que es necesario que seamos mas
especificos y tengamos que recurrir al uso de este.

Ejemplo

$usuarios = Load:: model ( 'usuario' )-> find_all_by_sql ( "select * from
usuarios where codigo not in (select codigo from ingreso)" )  
  
---  
  
En este ejemplo consultamos todos los usuarios con una sentencia where
especial. La idea es que los usuarios consultados no pueden estar en la
entidad ingreso.

####  5.4.1.3 find_by_sql (string $sql)

Este metodo nos permite hacer una consulta por medio de un SQL y el resultado
devuelto es un objeto que representa el resultado encontrado. La idea es que
el uso de este metodo no deberia ser comun en nuestras aplicaciones ya que
ActiveRecord se encarga de eliminar el uso del SQL en gran porcentaje, pero
hay momentos en que es necesario que seamos mas especificos y tengamos que
recurrir al uso de este.

Ejemplo

$usuario = Load:: model ( 'usuario' )-> find_by_sql ( "select * from usuarios
where codigo not in (select codigo from ingreso) limit 1" );  
  
---  
  
Este ejemplo consultamos todos los usuarios con una sentencia where especial e
imprimimos sus nombres. La idea es que el usuario consultado no puede estar en
la entidad ingreso.

####  5.4.1.4 find_first (string $sql)

Sintaxis

find_first([integer $id], [ "conditions: …" ], [ "order: …" ], [ "limit: …" ],
[ "columns: …" ])  
  
---  
  
El metodo "find_first" devuelve el primer registro de una entidad o la primera
ocurrencia de acuerdo a unos criterios de busqueda u ordenamiento. Los
parametros son todos opcionales y su orden no es relevante, cuando se invoca
sin parametros devuelve el primer registro insertado en la entidad. Este
metodo es muy flexible y puede ser usado de muchas formas:

Ejemplo

$usuario = Load:: model ( 'usuario' )-> find_first ( "conditions: estado='A' "
, "order: fecha desc" );  
  
---  
  
En este ejemplo buscamos el primer registro cuyo estado sea igual a "A" y
ordenado descendentemente, el resultado de este, se carga a la variable
$Usuarios e igualmente devuelve una instancia del mismo objeto ActiveRecord en
caso de exito o false en caso contrario.

Con el metodo find_first podemos buscar un registro en particular a partir de
su id de esta forma:

$usuario = Load:: model ( 'usuario' )-> find_first (123);  
  
---  
  
Asi obtenemos el registro 123 e igualmente devuelve una instancia del mismo
objeto. ActiveRecord en caso de exito o false en caso contrario. Kumbia genera
una advertencia cuando los criterios de busqueda para find_first devuelven mas
de un registro, para esto podemos forzar que se devuelva solamente uno,
mediante el parametro limit, de esta forma:

$usuario = Load:: model ( 'usuario' )-> find_first ( "conditions: estado='A' "
, "limit: 1" );  
  
---  
  
Cuando queremos consultar solo algunos de los atributos de la entidad podemos
utilizar el parametro columns  asi:

$usuario = Load:: model ( 'usuario' )-> find_first ( "columns: nombre, estado"
);  
  
---  
  
Cuando especificamos el primer parametro de tipo string , ActiveRecord asumira
que son las condiciones de busqueda para find_first, asi:

$usuario = Load:: model ( 'usuario' )-> find_first ( "estado='A'" );  
  
---  
  
De esta forma podemos tambien deducir que estas 2 sentencias arrojarian el
mismo resultado:

$usuario = Load:: model ( 'usuario' )-> find_first ( "id='123'" );  
  
---  
  
$usuario = Load:: model ( 'usuario' )-> find_first (123);  
  
---  
  
####  5.4.1.5 find ()

Sintaxis

find([integer $id], [ "conditions: …" ], [ "order: …" ], [ "limit: …], ["
columns: … "])  
  
---  
  
El metodo "find" es el principal metodo de busqueda de ActiveRecord, devuelve
todas los registros de una entidad o el conjunto de ocurrencias de acuerdo a
unos criterios de busqueda. Los parametros son todos opcionales y su orden no
es relevante, incluso pueden ser combinados u omitidos si es necesario. Cuando
se invoca sin parametros devuelve todos los registros en la entidad.

No hay que olvidarse de incluir un espacio despues de los dos puntos (:) en
cada parametro.

Ejemplo

$usuarios = Load:: model ( 'usuario' )-> find ( "conditions: estado='A'" ,
"order: fecha desc" );  
  
---  
  
En este ejemplo buscamos todos los registros cuyo estado sea igual a "A" y
devuelva estos ordenados descendentemente, el resultado de este es un array de
objetos de la misma clase con los valores de los registros cargados en ellos,
en caso de no hayan registros devuelve un array vacio.

Con el metodo find podemos buscar un registro en particular a partir de su id
de esta forma:

$usuario = Load:: model ( 'usuario' )-> find (123);  
  
---  
  
Asi obtenemos el registro 123 e igualmente devuelve una instancia del mismo
objeto ActiveRecord en caso de exito o false  en caso contrario. Como es un
solo registro no devuelve un array , sino que los valores de este se cargan en
la misma variable si existe el registro.

Para limitar el numero de registros devueltos, podemos usar el parametro limit
, asi:

$usuarios = Load:: model ( 'usuario' )-> find ( "conditions: estado='A'" ,
'limit: 5', 'offset: 1' );  
  
---  
  
Cuando queremos consultar solo algunos de los atributos de la entidad podemos
utilizar el parametro columns  asi:

$usuarios = Load:: model ( 'usuario' )-> find ( "columns: nombre, estado" );  
  
---  
  
Cuando especificamos el primer parametro de tipo string , ActiveRecord asumira
que son las condiciones de busqueda para find , asi:

$usuarios = Load:: model ( 'usuario' )-> find ( "estado='A'" );  
  
---  
  
Se puede utilizar la propiedad count  para saber cuantos registros fueron
devueltos en la busqueda.

Nota: No es necesario usar find('id: $id')  para el find, se usa directament
find($id)

5.4.1.5 select_one (string $select_query)

Este metodo nos permite hacer ciertas consultas como ejecutar funciones en el
motor de base de datos sabiendo que estas devuelven un solo registro.

$current_time = Load:: model ( 'usuario' )-> select_one ( "current_time" );  
  
---  
  
En el ejemplo queremos saber la hora actual del servidor devuelta desde MySQL
asi que podemos usar este metodo para esto.

####  5.4.1.6 select_one(string $select_query) (static)

Este metodo nos permite hacer ciertas consultas como ejecutar funciones en el
motor de base de datos, sabiendo que estas devuelven un solo registro. Este
metodo se puede llamar de forma estatica, esto significa que no es necesario
que haya una instancia de ActiveRecord para hacer el llamado.

$current_time = ActiveRecord:: select_one ( "current_time" )  
  
---  
  
En el ejemplo queremos saber la hora actual del servidor devuelta desde MySQL
asi que podemos usar este metodo para esto.

####  5.4.1.7 exists()

Este metodo nos permite verificar si el registro existe o no en la base de
datos mediante su id o una condicion.

$usuario = Load:: model ( 'usuario' );  
  
$usuario-> id  = 3;  
  
if ($usuario-> exists ()){  
  //El usuario con id igual a 3 si existe  
}  
  
Load:: model ( 'usuario' )-> exists ( "nombre='Juan Perez'" )  
Load:: model ( 'usuario' )-> exists (2); // Un Usuario con id->2?  
  
---  
  
####  5.4.1.8 find_all_by()

Este metodo nos permite realizar una busqueda por algun campo

$resultado = Load:: model ( 'producto' )-> find_all_by ( 'categoria' ,
'Insumos' );  
  
---  
  
####  5.4.1.9 find_by_*campo*()

Este metodo nos permite realizar una busqueda por algun campo usando el nombre
del metodo como nombre de este. Devuelve un solo registro.

$resultado = Load:: model ( 'producto' )-> find_by_categoria ( 'Insumos' );  
  
---  
  
####  5.4.1.10 find_all_by_*campo*()

Este metodo nos permite realizar una busqueda por algun campo usando el nombre
del metodo como nombre de este. Devuelve todos los registros que coincidan con
la busqueda.

$resultado = Load:: model ( 'producto' )-> find_all_by_categoria ( "Insumos"
);  
  
---  
  
###  5.4.2 Conteos y sumatorias

####  5.4.2.1 count()

Realiza un conteo sobre los registros de la entidad con o sin alguna condicion
adicional. Emula la funcion de agrupamiento count.

$numero_registros = Load:: model ( 'cliente' )-> count ();  
$numero_registros = Load:: model ( 'cliente' )-> count ( "ciudad = 'BOGOTA'"
);  
  
---  
  
####  
5.4.2.2 sum()

Realiza una sumatoria sobre los valores numericos de el atributo de alguna
entidad, emula la funcion de agrupamiento sum en el lenguaje SQL.

$suma = Load:: model ( 'producto' )-> sum ( "precio" );  
$suma = Load:: model ( 'producto' )-> sum ( "precio" , "conditions: estado =
'A'" );  
  
---  
  
####  5.4.2.3 count_by_sql()

Realiza una sumatoria utilizando lenguaje SQL.

$numero = Load:: model ( 'producto' )-> count_by_sql ( "select count(precio)
from producto, factura  where factura.codigo = 1124 \  
 and factura.codigo_producto = producto.codigo_producto" );  
  
---  
  
5.4.3 Promedios, maximo y minimo

5.4.4 Creacion, actualizacion y borrado de registros

5.4.5 Validaciones

5.4.6 Transacciones

5.4.7 Otros metodos

5.4.8 Callbacks ActiveRecord

5.4.9 Asociaciones

5.4.10 Paginadores

* * *