# Topics List

## Intro

- [Preface](preface.md#prefacio) 
  - [Special Thanks](preface.md#agradecimietos)
  - [About the Manual](preface.md#acerca-del-manual)
  - [About Kumbia](preface.md#acerca-de-kumbia)
  - [About the community](preface.md#sobre-la-comunidad)
  - [Why use KumbiaPHP Framework?](preface.md#porque-usar-kumbiaphp-framework)
  - [What does KumbiaPHP?](preface.md#qué-aporta-kumbiaphp)
- [Model, view, controller (MVC)](mvc.md#modelo,-vista,-controlador-mvc) 
  - [What is MVC?](mvc.md#que-es-mvc)
  - [How KumbiaPHP apply the MVC?](mvc.md#como-kumbiaphp-aplica-el-mvc)
  - [Additional information](mvc.md#más-información)
  - [Case study (example of change)](mvc.md#caso-practico-cambiar-ejemplo)

## How to get started

- [Install KumbiaPHP](to-install.md#instalar-kumbiaphp) 
  - [Requirements](to-install.md#requisitos)
  - [Configure Web server](to-install.md#configurar-servidor-web) 
    - [Enabling mod_rewrite of Apache on GNU/Linux (Debian, Ubuntu and derivatives)](to-install.md#habitando-mod_rewrite-de-apache-en-gnu/linux-debian,-ubuntu-y-derivados)
    - [Why is important Mod-Rewrite?](to-install.md#por-que-es-importante-el-mod-rewrite)
- [My first app with KumbiaPHP](first-app.md#mi-primera-aplicación-con-kumbiaphp) 
  - [Hello, KumbiaPHP!](first-app.md#hola,-kumbiaphp!)
  - [Controller](first-app.md#el-controlador)
  - [View](first-app.md#la-vista)
  - [KumbiaPHP and URLs](first-app.md#kumbiaphp-y-sus-urls)
  - [Add more content](first-app.md#agregando-mas-contenido)
  - [Repeating history](first-app.md#repitiendo-la-historia)

## MCV components

- [Controller](controller.md#el-controlador) 
  - [Front controller](controller.md#3.1.--------controlador-frontal) 
    - [3.1.1. Destripando el Front Controller](controller.md#3.1.1.--------destripando-el-front-controller)
    - [3.1.2. Front Controller por defecto](controller.md#3.1.2.--------front-controller-por-defecto)
    - [3.1.3. Constantes de KumbiaPHP](controller.md#3.1.3.--------constantes-de-kumbiaphp) 
      - [3.1.3.1. APP_PATH](controller.md#3.1.3.1.-app_path)
      - [3.1.3.2. CORE_PATH](controller.md#3.1.3.2.-core_path)
      - [3.1.3.3. PUBLIC_PATH](controller.md#3.1.3.3.-public_path)
  - [3.2. Las Acciones](controller.md#3.2.--------las-acciones) 
    - [3.2.1. Las acciones y las vistas](controller.md#3.2.1.--------las-acciones-y-las-vistas)
    - [3.2.2. Obtener valores desde una acción](controller.md#3.2.2.--------obtener-valores-desde-una-accion)
  - [3.3. Convenciones y Creación de un Controlador](controller.md#3.3.-convenciones-y-creacion-de-un-controlador) 
    - [3.3.1. Convenciones](controller.md#3.3.1.-convenciones)
    - [3.3.2. Creación de un Controlador](controller.md#3.3.2.-creacion-de-un-controlador)
    - [3.3.3. Clase AppController](controller.md#3.3.3.--------clase-appcontroller)
    - [3.3.4. Acciones y Controladores por defecto](controller.md#3.3.4.--------acciones-y-controladores-por-defecto)
  - [3.4. Filtros](controller.md#3.4.-filtros) 
    - [3.4.1. Filtros de Controladores](controller.md#3.4.1.-filtros-de-controladores) 
      - [3.4.1.1. initialize()](controller.md#3.4.1.1.-initialize)
      - [3.4.1.2. finalize()](controller.md#3.4.1.2.-finalize)
    - [3.4.2. Filtros de Acciones](controller.md#3.4.2.-filtros-de-acciones) 
      - [3.4.2.1. before_filter()](controller.md#3.4.2.1.-before_filter)
      - [3.4.2.2. after_filter()](controller.md#3.4.2.2.-after_filter)
- [La Vista](view.md#la-vista) 
  - [4.1 Pasando datos a la vista](view.md#4.1-pasando-datos-a-la-vista)
  - [4.2 Buffer de salida](view.md#4.2-buffer-de-salida)
  - [4.3 Template](view.md#4.3-template) 
    - [4.3.1 ¿Como crear un Template?](view.md#4.3.1-como-crear-un-template)
    - [4.3.2 ¿Como utilizar un template?](view.md#4.3.2-como-utilizar-un-template)
    - [4.3.3 Pasando datos al template](view.md#4.3.3-pasando-datos-al-template)
  - [4.4 Partial](view.md#4.4-partial) 
    - [4.4.1 ¿Como crear un partial?](view.md#4.4.1-como-crear-un-partial)
    - [4.4.2 ¿Como utilizar un partial?](view.md#4.4.2-como-utilizar-un-partial)
    - [4.4.3 Pasando datos a los partials](view.md#4.4.3-pasando-datos-a-los-partials)
  - [4.5 Agrupando en directorios](view.md#4.5-agrupando-en-directorios) 
    - [4.5.1 Ejemplo de agrupación de vista](view.md#4.5.1-ejemplo-de-agrupacion-de-vista)
    - [4.5.2 Ejemplo de agrupación de partial](view.md#4.5.2-ejemplo-de-agrupacion-de-partial)
    - [4.5.3 Ejemplo de agrupación de template](view.md#4.5.3-ejemplo-de-agrupacion-de-template)
  - [4.6 Tipos de respuestas](view.md#4.6-tipos-de-respuestas)
  - [4.7 Uso de cache en las vistas](view.md#4.7-uso-de-cache-en-las-vistas) 
    - [4.7.1 Cache de vistas](view.md#4.7.1-cache-de-vistas) 
      - [4.7.1.1 Grupos de vistas en cache](view.md#4.7.1.1-grupos-de-vistas-en-cache)
    - [4.7.2 Cache de templates](view.md#4.7.2-cache-de-templates)
    - [4.7.3 Cache de partials](view.md#4.7.3-cache-de-partials)
  - [4.8 Helpers](view.md#4.8-helpers) 
    - [4.8.1 Clase Html](view.md#4.8.1-clase-html) 
      - [Html::img()](view.md#html::img)
      - [Html::link()](view.md#html::link)
      - [Html::lists()](view.md#html::lists)
      - [Html::gravatar()](view.md#html::gravatar)
      - [Html::includeCss()](view.md#html::includecss)
      - [Html::meta()](view.md#html::meta)
      - [Html::includeMetatags()](view.md#html::includemetatags)
      - [Html::headLink()](view.md#html::headlink)
      - [Html::headLinkAction()](view.md#html::headlinkaction)
      - [Html::headLinkResource()](view.md#html::headlinkresource)
      - [Html::includeHeadLinks()](view.md#html::includeheadlinks)
    - [4.8.2. Clase Tag](view.md#4.8.2.-clase-tag) 
      - [Tag::css()](view.md#tag::css)
      - [Tag::js()](view.md#tag::js)
      - [Incluye un archivo JavaScript a la vista, partial o template](view.md#incluye-un-archivo-javascript-a-la-vista,-partial-o-template)
    - [](view.md#)
    - [4.8.3. Clase Form](view.md#4.8.3.-clase-form) 
      - [Form::open()](view.md#form::open)
      - [Form::openMultipart()](view.md#form::openmultipart)
      - [Form::close()](view.md#form::close)
      - [Form::input()](view.md#form::input)
      - [Form::text()](view.md#form::text)
      - [Form::pass()](view.md#form::pass)
      - [Form::textarea()](view.md#form::textarea)
      - [Form::label()](view.md#form::label)
      - [Form::hidden()](view.md#form::hidden)
      - [Form::dbSelect()](view.md#form::dbselect)
      - [Form::select()](view.md#form::select)
      - [Form::file()](view.md#form::file)
      - [Form::button()](view.md#form::button)
      - [Form::submitImage()](view.md#form::submitimage)
      - [Form::submit()](view.md#form::submit)
      - [Form::reset()](view.md#form::reset)
      - [Form::check()](view.md#form::check)
      - [Form::radio()](view.md#form::radio)
    - [Js](view.md#js) 
      - [Js::link ()](view.md#js::link-)
      - [Js::linkAction ()](view.md#js::linkaction-)
      - [Js::submit ()](view.md#js::submit-)
      - [Js::submitImage ()](view.md#js::submitimage-)
    - [Ajax](view.md#ajax) 
      - [Ajax::link()](view.md#ajax::link)
      - [Ajax::linkAction()](view.md#ajax::linkaction)
- [5 Modelos](model.md#5-modelos) 
  - [5.1 ActiveRecord](model.md#5.1-activerecord)
  - [5.2 Ejemplo sin ActiveRecord](model.md#5.2-ejemplo-sin-activerecord)
  - [5.3 Como usar los modelos](model.md#5.3-como-usar-los-modelos) 
    - [5.1 El Modelo extiende el ActiveRecord](model.md#5.1-el-modelo-extiende-el-activerecord)
    - [5.2 El Modelo extiende el ActiveRecord](model.md#5.2-el-modelo-extiende-el-activerecord)
  - [5.4 ActiveRecord API](model.md#5.4-activerecord-api) 
    - [5.4.1 Consultas](model.md#5.4.1-consultas) 
      - [5.4.1.1 distinct ()](model.md#5.4.1.1-distinct-)
- [array('A', 'I', 'N')](model.md#array'a',-'i',-'n') - [5.4.1.2 find_all_by_sql (string $sql)](model.md#5.4.1.2-find_all_by_sql-string-$sql) - [5.4.1.3 find_by_sql (string $sql)](model.md#5.4.1.3-find_by_sql-string-$sql) - [5.4.1.4 find_first (string $sql)](model.md#5.4.1.4-find_first-string-$sql) - [5.4.1.5 find ()](model.md#5.4.1.5-find-) - [5.4.1.6 select_one(string $select_query) (static)](model.md#5.4.1.6-select_onestring-$select_query-static) - [5.4.1.7 exists()](model.md#5.4.1.7-exists) - [5.4.1.8 find_all_by()](model.md#5.4.1.8-find_all_by) - [5.4.1.9 find_by_*campo*()](model.md#5.4.1.9-find_by_*campo*) - [5.4.1.10 find_all_by_*campo*()](model.md#5.4.1.10-find_all_by_*campo*) - [5.4.2 Conteos y sumatorias](model.md#5.4.2-conteos-y-sumatorias) - [5.4.2.1 count()](model.md#5.4.2.1-count) - [](model.md#) - [5.4.2.3 count_by_sql()](model.md#5.4.2.3-count_by_sql)

## Otros Componentes

- [7 Clases padre](parent-class.md#7-clases-padre) 
  - [7.1 AppController](parent-class.md#7.1-appcontroller)
  - [7.2 ActiveRecord](parent-class.md#7.2-activerecord) 
    - [7.2.1. Ventajas del ActiveRecord](parent-class.md#7.2.1.---------ventajas-del-activerecord)
    - [7.2.2. Crear un Modelo en Kumbia PHP Framework](parent-class.md#7.2.2.---------crear-un-modelo-en-kumbia-php-framework)
    - [7.2.3. Columnas y Atributos](parent-class.md#7.2.3.---------columnas-y-atributos)
    - [7.2.4. Llaves Primarias y el uso de IDs](parent-class.md#7.2.4.--------llaves-primarias-y-el-uso-de-ids)
    - [7.2.5. Convenciones en ActiveRecord](parent-class.md#7.2.5.---------convenciones-en-activerecord)
  - [View](parent-class.md#view)
- [8 Libs de KumbiaPHP](parent-class.md#8-libs-de-kumbiaphp) 
  - [Cache](parent-class.md#cache) 
    - [driver($driver=null)](parent-class.md#driver$driver=null)
    - [get($id, $group='default')](parent-class.md#get$id,-$group='default')
    - [save($value, $lifetime=null, $id=false, $group='default')](parent-class.md#save$value,-$lifetime=null,-$id=false,-$group='default')
    - [start ($lifetime, $id, $group='default')](parent-class.md#start-$lifetime,-$id,-$group='default')
    - [end ($save=true)](parent-class.md#end-$save=true)
  - [Logger](parent-class.md#logger) 
    - [Logger::warning ($msg);](parent-class.md#logger::warning-$msg;)
    - [Logger::error ($msg)](parent-class.md#logger::error-$msg)
    - [Logger::debug ($msg)](parent-class.md#logger::debug-$msg)
    - [Logger::alert ($msg)](parent-class.md#logger::alert-$msg)
    - [Logger::critical ($msg)](parent-class.md#logger::critical-$msg)
    - [Logger::notice ($msg)](parent-class.md#logger::notice-$msg)
    - [Logger::info ($msg)](parent-class.md#logger::info-$msg)
    - [Logger::emergence ($msg)](parent-class.md#logger::emergence-$msg)
    - [Logger::custom ($type='CUSTOM', $msg)](parent-class.md#logger::custom-$type='custom',-$msg)
  - [Flash](parent-class.md#flash) 
    - [Flash::error($text)](parent-class.md#flash::error$text)
    - [Flash::valid($text)](parent-class.md#flash::valid$text)
    - [Flash::info($text)](parent-class.md#flash::info$text)
    - [Flash::warning($text)](parent-class.md#flash::warning$text)
    - [Flash::show($name, $text)](parent-class.md#flash::show$name,-$text)
  - [Session](parent-class.md#session) 
    - [Session::set($index, $value, $namespace='default')](parent-class.md#session::set$index,-$value,-$namespace='default')
    - [Session::get($index, $namespace='default')](parent-class.md#session::get$index,-$namespace='default')
    - [Session::delete($index, $namespace='default')](parent-class.md#session::delete$index,-$namespace='default')
    - [Session::has($index, $namespace='default')](parent-class.md#session::has$index,-$namespace='default')
  - [Load](parent-class.md#load) 
    - [Load::coreLib($lib)](parent-class.md#load::corelib$lib)
    - [Load::lib($lib)](parent-class.md#load::lib$lib)
    - [Load::model($model)](parent-class.md#load::model$model)
  - [Auth2](parent-class.md#auth2) 
    - [Solicitando un adaptador](parent-class.md#solicitando-un-adaptador)
    - [Adaptador predeterminado](parent-class.md#adaptador-predeterminado)
    - [Como trabaja la autenticación](parent-class.md#como-trabaja-la-autenticacion)
    - [Adaptador Model](parent-class.md#adaptador-model) 
      - [setModel()](parent-class.md#setmodel)
      - [identify()](parent-class.md#identify)
      - [logout()](parent-class.md#logout)
      - [setFields()](parent-class.md#setfields)
      - [setSessionNamespace()](parent-class.md#setsessionnamespace)
      - [isValid()](parent-class.md#isvalid)
      - [getError()](parent-class.md#geterror)
      - [setAlgos()](parent-class.md#setalgos)
      - [setKey()](parent-class.md#setkey)
      - [setCheckSession()](parent-class.md#setchecksession)
      - [setPass()](parent-class.md#setpass)
      - [setLogin()](parent-class.md#setlogin)
      - [Obtener los campos cargados en sesión](parent-class.md#obtener-los-campos-cargados-en-sesion)
      - [Ejemplo](parent-class.md#ejemplo)
- [The console](console.md#la-consola) 
  - [Intro](console.md#introduccion)
  - [How to use the console](console.md#como-utilizar-la-consola)
  - [KumbiaPHP consoles](console.md#consolas-de-kumbiaphp) 
    - [Cache](console.md#cache) 
      - [clean \[group\] \[--driver\]](console.md#clean-[group]-[--driver])
    - [Clean the cache.](console.md#permite-limpiar-la-cache.)
    - [Sequential arguments:](console.md#argumentos-secuenciales:)
    - [Named arguments:](console.md#argumentos-con-nombre:)
    - [Example:](console.md#ejemplo:)
    - [php ../../core/console/kumbia.php cache clean](console.md#php-../../core/console/kumbia.php-cache-clean) 
      - [remove \[id\] \[group\]](console.md#remove-[id]-[group])
    - [Model](console.md#model) 
      - [create [model]](console.md#create-[model])
      - [delete [model]](console.md#delete-[model])
    - [Controller](console.md#controller) 
      - [create [controller]](console.md#create-[controller])
      - [delete [controller]](console.md#delete-[controller])
  - [](console.md#)
  - [Developing your consoles](console.md#desarrollando-tus-consolas) 
    - [Console::input](console.md#console::input)

## Appendix

- [Apéndices](appendix.md#apendices) 
  - [Integration of jQuery and KumbiaPHP](appendix.md#integracion-de-jquery-y-kumbiaphp) 
    - [KDebug](appendix.md#kdebug)
  - [CRUD](appendix.md#crud) 
    - [Intro](appendix.md#introducción)
    - [Configuring database.ini](appendix.md#configurando-database.ini)
    - [Model](appendix.md#modelo)
    - [Controller](appendix.md#controller)
    - [Views](appendix.md#vistas)
    - [Testing the CRUD](appendix.md#probando-el-crud)
  - [Application in production](appendix.md#aplicacion-en-producción)
  - [Partials for pagination](appendix.md#partials-de-paginacion) 
    - [Classic](appendix.md#classic)
    - [Digg](appendix.md#digg)
    - [Extended](appendix.md#extended)
    - [PunBB](appendix.md#punbb)
    - [Simple](appendix.md#simple)
    - [Sample Usage](appendix.md#ejemplo-de-uso)
  - [Auth](appendix.md#auth)
  - [Beta1 to Beta2](appendix.md#beta1-a-beta2)
  - [Deprecated](appendix.md#deprecated)
  - [Methods and classes that were used in previous versions and still](appendix.md#metodos-y-clases-que-se-usaban-en-versiones-anteriores-y-que-aun) 
    - [List of changes between versions: If don't specify beta1 is that it is](appendix.md#lista-de-cambios-entre-versiones:-si-no-se-especifica-beta1-es-que-es)
    - [Change in the routes between versions:](appendix.md#cambio-en-las-rutas-entre-versiones:)
- [0.5 => 1.0 beta1](appendix.md#0.5-=>-1.0-beta1)
- [1.0 beta1 => 1.0 beta2](appendix.md#1.0-beta1-=>-1.0-beta2) 
  - [Glossary](appendix.md#glosario)