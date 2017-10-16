- [Intro](#intro)
- [Empezando](#empezando)
- [Sintaxis](#sintaxis)
- [Objetos](#objetos)
- [Filtros](#filtros)
- [Configuración](#configuracion)

***

<a name="intro"></a>
# Temas

Si estás buscando cómo crear, personalizar o extender un tema, has llegado al lugar correcto. Seas un programador que está empezando o un experto, tenemos todo lo que necesitas para empezar a construir excelentes temas utilizando todas nuestras herramientas.

---

<a name="empezando"></a>
## Empezando

Cualquier tema de Shoperti consiste de varias páginas construidas con HTML, CSS y Javascript y una combinación de filtros y objetos. Por el momento, todos los cambios que se realizan al tema de una tienda, deben de ser hechos en la sección de Editar HTML y CSS de los temas.

> **¿No eres programador?** Si estás buscando cómo instalar y personalizar temas, [consulta nuestra sección de personalización de temas](/ayuda/manual/temas)

Nuestos temas cumplen con la siguiente estructura:

```
├── assets
│   └── // Javascripts, CSS, e imágenes del tema
│
├── config
│   ├── data.json
│   └── schema.json
│
├── layouts
│   └── layout.twig
│
├── pages
│   ├── customers (requerido si las cuentas de clientes están habilitadas)
│   │   ├── account.twig
│   │   ├── activate.twig
│   │   ├── login.twig
│   │   ├── order.twig
│   │   ├── recover.twig
│   │   ├── register.twig
│   │   └── reset.twig
│   │
│   ├── blog.twig
│   ├── cart.twig
│   ├── category.twig
│   ├── collection.twig
│   ├── collections.twig
│   ├── error404.twig
│   ├── home.twig
│   ├── maintenance.twig
│   ├── page.twig
│   ├── password.twig
│   ├── post.twig
│   ├── product.twig
│   ├── products.twig
│   └── search.twig
│
├── partials
│   └── // Subplantillas reutilizables por layouts y/o páginas
│
├── screenshot.png
│
└── settings.json
```

#### Assets

En este directorio podrás guardar cualquier archivo que deba ser publicable, por ejemplo: imágenes, javascript y css. Y puedes usar el filtro de `asset_url` para acceder a la ruta del archivo.

#### Config

En el directorio de `config` encontrarás las variables necesarias para poder personalizar el tema utilizando nuestro personalizar. Incluye un archivo `schema.json` el cual contiene la estructura de las variables y `data.json` que guarda las variables para su uso.

#### Layouts

En este directorio puedes crear diferentes diseños, los cuales puedes extender. Incluye un archivo llamado `layout.twig`.

#### Partials

Para poder reusar tu código, puedes armar pequeños fragmentos e incluirlos en varios espacios y así aprovechar su reusabilidad.

#### Pages

Aquí encontrarás cada una de las secciones con las cuales puedes modificar el contenido específico de una página.

| Página                  | Descripción                                                                     |
|-------------------------|---------------------------------------------------------------------------------|
| blog.twig               | La forma en la que se despliega el listado de artículos del blog de una tienda. |
| cart.twig               | La forma en la que ves el carrito de compras de la tienda.                      |
| category.twig           | En esta vista podrás ver los productos ordenados por categoría.                 |
| collection.twig         | En esta vista podrás ver los productos que contiene una colección.              |
| collections.twig        | En esta vista podrás ver todas las colecciones de una tienda.                   |
| customers/account.twig  | Despliega la forma en la que un cliente de la tienda ve los datos de su cuenta. |
| customers/activate.twig | Despliega la forma en la que un cliente activa su cuenta.                       |
| customers/login.twig    | Despliega la forma en la que un cliente inicia sesión en la tienda.             |
| customers/order.twig    | En esta vista el usuario puede ver el detalle de una orden en especifico.       |
| customers/recover.twig  | Despliega la forma en la que un cliente puede recuperar su contraseña.          |
| customers/register.twig | Despliega la forma en la que un cliente puede registrar su cuenta.              |
| customers/reset.twig    | Despliega la forma en la que un cliente puede cambiar su contraseña.            |
| error404.twig           | Esta vista se despliega cuando lo que se está buscando en la tienda no existe.  |
| home.twig               | Vista principal cuando se abre la tienda.                                       |
| maintenance.twig        | Cuando la tienda está en mantenimiento se despliega esta vista.                 |
| page.twig               | En esta vista podrás ver el contenido de una página. 						    |
| password.twig           | Cuando la tienda tiene contraseña se despliega esta vista.                      |
| post.twig               | En está vista podrás ver el contenido de una artículo.                          |
| product.twig            | En está vista podrás ver la información de un producto y sus variantes.         |
| products.twig           | La forma en la que se despliega el listado de productos de una tienda.          |
| search.twig             | Despliega la forma en la que se muestran los resultados de cualquier búsqueda.  |

### Páginas Alternas

Al crear páginas con un nombre alterno, puedes tener diferentes versiones del contenido. Un ejemplo es:

`page.contact.twig`

Esto habilitará en el adminsitrador una sección especial para que se pueda elegir la alternativa y así crear más dinamismo.

---

<a name="sintaxis"></a>
## Sintaxis

Nuestros temas están basados en el motor de plantillas llamado [Twig](http://twig.sensiolabs.org/) el cual consiste de objetos, filtros y tags. Los objetos son pedazos de datos relevantes a tu tienda, como por ejemplo productos e información de carritos. Los filtros, son métodos simples que dan formato a los datos, como el capitalizar textos o dar formato a la moneda. Las tags, permiten agregar lógica específica sobre algún dato, como por ejemplo saber si el producto cuenta con inventario disponible o no. En esta sección podrás encontrar la documentación de cada uno de ellos.

#### Objetos

Los objetos son pedazos de datos relevantes a tu tienda. Puedes usar estos objetos en tu código para mostrar información especifica sobre los datos de tu tienda. Para usar objetos envuélvelos en dos corchetes de cada lado.

```twig
Bienvenido a la tienda {{ store.name }}
La imagen del producto es {{ product.image_url }}
<a href="{{ page.permalink }}">{{ page.title }}</a>
```

#### Filtros

Los filtros son métodos simples que dan formato a los datos. El primer parámetro es el valor inicial y utilizando una barra, puedes agregar varios filtros de izquierda a derecha.

```twig
{{ product.price | money }}
{{ page.title | capitalize }}
{{ products | json }}
```

#### Tags

Las tags son la lógica en tu HTML y son envueltas en corchetes y un signo de porcentaje.

```twig
{% if product.in_stock %}
{% for products in cart.items %}
{% include 'section.twig' %}
```

#### If, Else y Elseif

Estas tags muestran contenido dependiendo de diferentes condiciones.

```twig
{% if product.in_stock %}
	Producto disponible
{% endif %}

{% if product.description is empty %}
	Nada que ver aquí
{% endif %}

{% if product.compare_price > 0 %}
	¡Producto en descuento!
{% else %}
	Producto a precio normal
{% endif %}

{% if cart.items.count == 0 %}
	No hay artículos en el carrito.
{% endif %}

# templates = ['blog', 'pages', 'products']
{% if 'blog' in templates %}
	Estás viendo el blog.
{% endif %}
```

#### Ciclos usando For

```twig
{% for post in blog.posts %}
  Post: {{ post.title }}
{% endfor %}

{% for item in cart.items %}
  Artículo: {{ item.name }}
{% endfor %}
```

Los ciclos tienen variables de apoyo que pueden ayudar a definir comportamiento de cada uno de ellos.

```twig
loop.index     => La iteración actual empezando en 1
loop.index0    => La iteración actual empezando en 0
loop.revindex  => El número de iteraciones desde el final del ciclo empezando en 1
loop.revindex0 => El número de iteraciones desde el final del ciclo empezando en 0
loop.first     => Cierto en la primera iteración
loop.last      => Cierto en la última iteración
loop.length    => La cantidad de artículos a iterar 
```

Limitar ciclo con una condición.

```twig
{% for product in products if product.in_stock %}
    Producto: {{ product.name }}
{% endfor %}
```

Usar `else` en caso que el ciclo esté vacio.

```twig
{% for items in cart.items %}
    Producto: {{ items.name }}
{% else %}
	No hay productos.
{% endfor %}
```

Iterando sobre rangos específicos.

```twig
{% for i in 1..product.images.count %}
  Imagen {{ i }}
{% endfor %}
```

---

<a name="objetos"></a>
## Objetos

Los objetos imprimen atributos que son dinámicos en el contenido de las páginas. Por ejemplo, el objeto `product` tiene un atributo llamado `name` que puede usarse para desplegar el nombre de un producto.

```twig
{{ product.name }} # => "Collar de perlas"
```

#### Objetos globales

Los objetos globales son objetos a los cuales se puede acceder en cualquier archivo de tu tema.

##### all_products

Contiene todos los productos de la tienda. Puedes usar este objeto ingresando mediante el permalink del producto.

```twig
{{ all_products['collar-de-perlas'].name }} # => "Collar de perlas"
```

##### blogs

Contiene todos los productos de la tienda. Puedes usar este objeto ingresando mediante el permalink del producto.

```twig
{{ blogs['noticias'].name }} # => "Noticias"
{% for post in blog.noticias.posts %}
	{{ post.title }}
{% endfor %}
```

##### canonical_url

El objeto `canonical_url` contiene la URL canónica completa de la sección actual que estás visitando.

```twig
{{ canonical_url }} # => "http://ejemplo.com/productos/collar-de-perlas"
```

##### cart

El objeto `cart` contiene todos los productos que el cliente ha agregado a su carrito de compras, así como un resumen de sus totales.

```twig
{{ cart.items }}
{{ cart.total_items }}
{{ cart.total_price }}
{{ cart.total_compared_price }}
{{ cart.customer_note }}
```

##### collections

El objeto `collections` contiene todas las colecciones disponibles en la tienda. Puedes usar este objeto ingresando mediante el permalink de la colección.

```twig
{% for product in collections.incio.products %}
  {{ product.title }}
{% endfor %}
```

##### current_page

El objeto `current_page` contiene la página actual que el cliente está navegando cuando el contenido es paginable.

```twig
{% if current_page != 1 %}
  Página {{ current_page }}
{% endif %}
```

##### current_tags

El objeto `current_tags` contiene los tags de la sección actual que el cliente está navegando cuando el contenido puede contener tags. Un ejemplo es en la sección de productos y de artículos del blog. 

```twig
# post.twig
{% if current_tags %}
  <h1>{{ post.title }} &rsaquo; {{ current_tags | join(', ') }}</h1> # => 'Hola Mundo › empezando, nuevo'
{% endif %}
```

##### customer

El objeto `customer` contiene el cliente actual que ha iniciado sesión en la tienda. 

```twig
{% if customer %}
	<a href="/cuenta/salir">Salir</a>
{% else %}
	<a href="/cuenta/login">Iniciar Sesión</a>
{% endif %}
```

##### menus

El objeto `menus` contiene todos los menús dados de alta en la tienda. Puedes acceder a ellos por medio de su permalink.

```twig
<ul>
  {% for link in menus.footer %}
    <li><a href="{{ link.url }}">{{ link.name }}</a></li>
  {% endfor %}
</ul>
```

##### pages

El objeto `pages` contiene una lista de todas las páginas disponibles en la tienda. Puedes acceder a ellas por medio de su permalink.

```twig
<h1>{{ pages['inicio'].title }}</h1>
```

##### page_description

El objeto `page_description` contiene la descripción del producto, colección o página que se está visitando.

```twig
{% if page_description %}
  <meta name="description" content="{{ page_description }}" />
{% endif %}
```

##### page_title

El objeto `page_title` contiene el título de la página que se está visitando.

```twig
<meta name="title" content="{{ page_title }}" />
```

##### store

El objeto `store` contiene toda la información pública sobre la tienda.

```twig
<meta name="title" content="{{ store.name }}" />
{{ store.currency }}
```

##### settings

El objeto `settings` contiene las variables configuradas del tema activo para personalización.

```twig
{% if settings.use_favicon %}
  <link rel="shortcut icon" href="{{ settings.favicon }}" type="image/png" />
{% endif %}
```

##### template

El objeto `template` contiene el nombre del archivo cargado en la página actual, sin incluir la extesión `.twig`. 

```twig
{% if 'product' in template %}
  <meta property="og:type" content="product" />
{% endif %}
```

#### Otros Objetos

##### head_content

Esté objeto sólo se tiene que cargar en la sección `<head></head>` dentro de cualquier `layout` que se esté cargando, ya que Shoperti carga contenido dinámico en cada página como Google Analytics y más.

---

<a name="filtros"></a>
## Filtros

#### Arreglos

Cuenta los elementos en el arreglo.

```twig
{% set tallas = ['s', 'm', 'l'] %}
{{ tallas | length }} # => 3
```

Toma el primer elemento de un arreglo.

```twig
{% set tallas = ['s', 'm', 'l'] %}
{{ tallas | first }} # => 's'
```

Junta los elementos de un arreglo por medio de un elemento.

```twig
{{ tallas | join(', ') }} # => 's', 'm', 'l'
```

Toma las llaves del arreglo

```twig
{% set opciones = [0 => 's', 1 => 'm', 2 => 'l'] %}
{{ opciones | keys }} # => 0, 1, 2
```

Divide un arreglo en pedazos.

```twig
{{ [1, 2, 3, 4, 5, 6] | batch(2) }} # => [1, 2, 3] [4, 5, 6] 
```

Toma una secuencia definida.

```twig
{{ [1, 2, 3, 4, 5] | slice(1, 2) }} # => Itera desde el 2 al 3
```

Junta dos arreglos.

```twig
{% set tallas = ['s', 'm'] %}
{{ set tallas = tallas | merge(['l', 'xl']) }} # => ['s', 'm', 'l', 'xl']
```

Imprime un arreglo en formato `JSON`.

```twig
{% set tallas = ['s', 'm', 'l'] %}
{{ tallas | json }} => {'s', 'm', 'l'}
```

Imprime un arreglo en formato `JSON` de forma legible.

```twig
{% set tallas = ['s', 'm', 'l'] %}
{{ tallas | json }} => 
{
	's', 
	'm', 
	'l'
}
```

#### HTML

```twig
{{ 'imagen.jpg' | img_tag }} # => <img src="imagen.jpg" alt="" />
```

```twig
{{ 'app.js' | script_tag }} # => <script src="app.js"></script>
```

```twig
{{ 'styles.css' | style_tag }} # => <link href="style.css" rel="stylesheet" type="text/css" />
```

#### Dinero

Los filtros de dinero, utilizan la configuración de la tienda para mostrar su formato.

Da formato a un número en moneda.

```twig
{{ 100 | money }} # => '100.00'
```

Da formato a un número en moneda e incluye el símbolo de la moneda configurada en la tienda.

```twig
{{ 100 | money('symbol') }} # => '$100.00'
{{ 100 | money_with_symbol }} # => '$100.00'
```

Da formato a un número en moneda e incluye el código de la moneda configurada en la tienda.

```twig
{{ 100 | money('code') }} # => '100.00 MXN'
{{ 100 | money_with_code }} # => '100.00 MXN'
```

Da formato a un número en moneda e incluye el símbolo y código de la moneda configurada en la tienda.

```twig
{{ 100 | money('symbol', 'code') }} # => '$100.00 MXN'
{{ 100 | money_with_symbol_and_code }} # => '$100.00 MXN'
```

#### Cadenas

Capitaliza la primera palabra de una cadena.

```twig
{{ "producto ejemplo" | capitalize }} # => "Producto Ejemplo"
```

Capitaliza la primer letra de cada palabra de una cadena.

```twig
{{ "el libro amarillo" | title }} # => "El Libro Amarillo"
```

Convierte una cadena en minúsiculas.

```twig
{{ "PRODUCTO" | lower }} # => "producto"
```

Convierte una cadena en mayúsculas.

```twig
{{ "producto" | upper }} # => "PRODUCTO"
```

Remueve caracteres especiales de una cadena.

```twig
{{ '<p>prueba</p>' | escape }} # => "<p>prueba</p>"
```

Inserta un `<br>` en cada salto de línea en una cadena.

```twig
{% set cadena = '
Uno
Dos
' %}
{{ cadena | nl2br }}
Uno <br>
Dos <br>
```

Imprime cadenas con caracteres especiales.

```twig
{{ '<p>prueba</p>' | raw }} # => "prueba"
```

Remplaza una cadena dentro de otra.

```twig
{{ "Me gusta la %esto%." | replace({ '%esto%': 'camisa' }) }} # => "Me gusta la camisa."
```

Remueve una cadena dentro de otra.

```twig
{{ "Me gusta la camisa." | remove('la camisa') }} # => "Me gusta."
```

Separa una cadena en un arreglo.

```twig
{{ "uno,dos,tres" | split(',') }} # => ['uno', 'dos', 'tres']
```

Remueve el espacio muerto al principio y al final de una cadena.

```twig
{{ "    hola como estas      " | trim }} # => "hola como estas"
```

Trunca las letras de una cadena con el número de caracteres que definas.

```twig
{{ "Mis productos son los mejores." | truncate(13) }} # => "Mis productos..."
```

Trunca las palabras de una cadena con el número de palabras que definas.

```twig
{{ "Mis productos son los mejores." | truncate_words(3) }} # => "Mis productos son..."
```

Remueve los tags de HTML de una cadena.

```twig
{{ '<p>prueba</p>' | striptags }} # => "prueba"
```

#### URL

Imprime el URL a cualquier archivo que exista en la carpeta `assets` del tema.

```twig
{{ 'logo.png' | asset_url }} # => https://cdn-myshoperti.global.ssl.fastly.net/demo/jurban/1.0.0/assets/logo.png
```

Imprime el URL a cualquier archivo que exista los archivos de la tienda.

```twig
{{ 'ebook.pdf' | files_url }} # => https://cdn-myshoperti.global.ssl.fastly.net/demo/files/ebook.pdf
```

Imprime el URL de los archivos globales de Shoperti.

```twig
{{ 'sku-select/v1/sku-select.min.js' | global_asset_url }} # => https://cdn-shoperti.global.ssl.fastly.net/global/libs/sku-select/v1/sku-select.min.js
```

Imprime el URL de las imágenes globales de Shoperti.

```twig
{{ 'placeholders/product-11.jpg' | global_img_url }} # => https://cdn-shoperti.global.ssl.fastly.net/global/img/placeholders/product-11.jpg
```

Imprime el URL de las imágenes de pago globales de Shoperti.

```twig
{{ 'visa.png' | payment_img_url }} # => https://cdn-shoperti.global.ssl.fastly.net/global/img/payments/visa.png
```

#### Extras

Define una valor por defecto.

```twig
{{ product.description | default('Sin descripción.') }}
```

Da formato legible a las fechas.

```twig
{{ post.published_at | date }}  # => "2 noviembre 2016"
```

Da formato legible a las fechas con su hora.

```twig
{{ post.published_at | datetime }} # => "2 noviembre 2016 16:42:00"
```

Convierte diferentes unidades de peso de archivo.

```twig
{{ 10000000 | filesize }} # => "9.54MB"
{{ 1000000000 | filesize('gb') }} # => "0.93GB"
```

Convierte diferentes unidades de peso de archivo sin símbolo.

```twig
{{ 10000000 | filesize_without_unit }} # => "9.54"
```

Convierte diferentes unidades de peso.

```twig
{{ 10000 | weight }} # => "10 kg"
{{ 10000 | weight('lb') }} # => "22.05 lb"
```

Convierte diferentes unidades de peso sin símbolo.

```twig
{{ 10000 | weight_without_unit }} # => "10"
{{ 10000 | weight_without_unit('lb') }} # => "22.05"
```

Calcula un color más obscuro dependiendo de un porcentaje definido.

```twig
{{ '#fffff' | darken_color }} # => "#d8d800"
```

Calcula un color más claro dependiendo de un porcentaje definido.

```twig
{{ '#000000' | lighten_color(30) }} # => "#4c4c4c"
```

Calcula un color opuesto.

```twig
{{ '#000000' | contrast_color }} # => "#ffffff"
```

> **NOTA** Si quieres ver más documentación sobre los filtros puedes visitar [Twig Filters](http://twig.sensiolabs.org/doc/filters/index.html)

---

<a name="configuracion"></a>
## Archivos de configuración

Para hacer que un tema sea configurable desde la funcionalidad de **Personalizar** se deben agregar dos archivos de /config: `schema.json` y `data.json`. `schema.json` contiene la estructura que modela las opciones personalizables y `data.json` contiene estilos preconfigurados y eventualmente almacenará también las configuraciones que se personalicen desde el editor de la tienda.


#### Anatomía del archivo schema.json

```json
{
  "info" : {
    "logo" : "nav_logo",
    "header" : "Tenue Theme",
    "content" : [
      "Lineas con información del tema.",
      "Cada línea es un parrafo dentro de la zona de información del tema."
    ]
  },
  "categories": [
    {
      "name" : "Colores",
      "sections" : [
        {
          "header" : "Textos",
          "settings" : [
              // {ajustes}
          ]
        }
      ]
    }
  ]
}
```

#### Tipos de ajustes

##### Parrafo

```json
{
  "type"    : "paragraph",
  "content" : "Este es un párrafo de texto"
}
```


##### Texto

```json
{
  "type"    : "text",
  "id"      : "body_font_size",
  "label"   : "General",
  "default" : "18px"
}
```


##### Texto (area de texto)

```json
{
  "type"    : "textarea",
  "id"      : "footer_contact_data",
  "label"   : "Información de contacto",
  "default" : "Calle Principal #10\n+52 1 123 456 7890",
  "info"    : "Calle Principal #10"
}
```


##### Checkbox

```json
{
  "type"  : "checkbox",
  "id"    : "use_logo",
  "label" : "Usar logo personalizado"
}
```


##### Selector de opciones

```json
{
  "type"    : "select",
  "id"      : "base_font",
  "label"   : "Base",
  "options" : [
    {
      "value" : "\"Open Sans\", sans-serif",
      "label" : "Open Sans",
      "group" : "Web Fonts"
    }
  ]
}
```


##### Color

```json
{
  "type"    : "color",
  "id"      : "brand_main_color",
  "label"   : "Primario",
  "default" : "#979797"
}
```


##### Selector de una colección

```json
{
  "type"    : "collection",
  "id"      : "featured_collection_1",
  "label"   : "Colección Destacada 1",
  "default" : "inicio"
}
```


##### Selector de un blog

```json
{
  "type"  : "blog",
  "id"    : "featured_blog",
  "label" : "Elige un Blog"
}
```


##### Selector de una imagen

```json
{
  "type"  : "image",
  "id"    : "nav_logo",
  "label" : "Seleccionar Logo"
}
```

#### Cómo definir íconos para las categorías del tema

Lista de íconos usables:

- presets
- colors
- typography
- header
- footer
- home page
- product page
- collection page
- blog page
- cart page
- social media
