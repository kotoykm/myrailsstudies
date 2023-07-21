# Hola
Este es un archivo de estudios personal. Su objetivo es compilar todo el conocimiento necesario para usar Ruby on Rails.

Todo el contenido que falte aquí será actualizado hasta completarse. Cosas específicas serán subidas como proyectos del tipo "Como usar active_storage", "Como crear usuarios", "Como hacer formularios manualmente", etc.

Si quieres contribuir hazle fork este repositorio y crea tu propio proyecto de Rails dentro, con su respectivo README.MD

De la siguiente forma:

    myrailsStudies/
    |
    ├─ mysiteErick/
    |
    ├─ tusitioTuNombre/
    │  ├─ README.md
    |
    ├─ README.md (Ubicación actual)

Guia para hacer fork y pull request: https://www.freecodecamp.org/espanol/news/como-hacer-tu-primer-pull-request-en-github/

---

## Links de interés

Rutas de rails

http://localhost:3000/rails/info/routes

Documentación de Ruby para mi versión (3.1.3)

https://ruby-doc.org/3.1.3/

Documentación de Rails para la versión más actual (7.0.6)

https://api.rubyonrails.org/

Rails Inflector 

https://api.rubyonrails.org/classes/ActiveSupport/Inflector.html

---
## Comandos
**Crear proyecto con base de datos predeterminada:**

    rails new ["nombre del proyecto"] -d postgresql
**Crear un controlador**
(Sus nombres deben estar siempre en plural)

    rails g controller ["NombreControlador] ["Vista1"] ["Vista2"] etc.


**Invocar todas las rutas**

    rails routes

**Crear modelos** (Deben ir siempre en singular)

    rails g model [modeName] [colName1] [colName2] etc...


## Migraciones

**Crear una base de datos**

    rails:db create

**Correr una migración**

    rails:db migrate

**El mounstruo** (Es un reseteador mejor que rails db:reset. La seed es opcional)

    rails db:drop db:create db:migrate db:seed

**Actualizar** (Sin se especifican la columna y el tipo)
Esto solo generará el archivo de migración. No hará nada hasta que ejecutemos la migración.

    rails g migration addColumnToModel column:datatype

**Volver atrás en una migración**

    rails db:rollback

**Revisar el estado de todas las migraciones**

    rails db:migrate:status


---
## Helpers
**Usar el tiempo actual**
Usar sus derivados

https://ruby-doc.org/3.1.3/Time.html#method-c-now

	<%= Time.now.year %>

**link_to**

https://api.rubyonrails.org/classes/ActionView/Helpers/UrlHelper.html#method-i-link_to

    <%= link_to("texto", [ruta], [opciones]) %>

**asset_path**

https://api.rubyonrails.org/classes/ActionView/Helpers/AssetUrlHelper.html#method-i-asset_path

    asset_path(source, options = {})

**image_tag**

https://api.rubyonrails.org/classes/ActionView/Helpers/AssetTagHelper.html#method-i-image_tag

    image_tag(source, options = {})

**Helper para incluir Javascript**

https://api.rubyonrails.org/classes/ActionView/Helpers/AssetTagHelper.html#method-i-javascript_include_tag

    javascript_include_tag(*sources)

---
## Consolas

**Consola web**

    rails s -p [numero_puerto, ej: 3001]

**Consola de base de datos** (El postgresqlshell)

    rails db

**Consola de Ruby**

    rails c

---

## Misc.

**Tipos de datos comunes**

    column:integer

    column:string

    column:text

    column:datetime

    column:boolean

**Códigos comunes para Rails Console**

```ruby
    #Se usará como ejemplo un objeto Product

    #Lista todos los productos
    Product.all

    #Listar solo el primero o el último
    Product.first
    Product.last

    #Encontrar un producto específico por ID
    Product.find(1) #La id puede ser cualquiera

    #Eliminar un producto específico
    Product.find(1).destroy #Eliminará el primer producto

    #Crear producto por medio de sus atributos
    Product.create(:atrr1, :attr2, :attr3, :arrtetc)
```