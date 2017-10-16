- [Intro](#intro)
- [Objeto de Producto](#objeto-de-producto)
- [Consultar todos los Productos](#consultar-todos-los-productos)
- [Consultar un Producto](#consultar-un-producto)
- [Crear un Producto](#crear-un-producto)
- [Actualizar un Producto](#actualizar-un-producto)
- [Consultar categorías de un producto](#consultar-categorias-de-un-producto)
- [Agregar categorías a un producto](#agregar-categorias-a-un-producto)
- [Eliminar un Producto](#eliminar-un-producto)

***

<a name="intro"></a>
# Productos API

Productos representan el listado de productos en una tienda.

---

<a name="objeto-de-producto"></a>
## Objeto de Producto

| Atributo           | Tipo      | Descripión                                                                    |
|--------------------|-----------|-------------------------------------------------------------------------------|
| `id`               | cadena    | Identificador único del producto.                                             |
| `object`           | cadena    | El nombre del tipo de objeto.                                                 |
| `permalink`        | cadena    | El permalink único del producto.                                              |
| `name`             | cadena    | El nombre del producto.                                                       |
| `excerpt`          | cadena    | Una descripción corta sobre el producto.                                      |
| `description`      | cadena    | Descripción completa del producto.                                            |
| `price`            | entero    | El precio de venta del producto.                                              |
| `compared_price`   | entero    | El precio en descuento del producto.                                          |
| `modifiers[]`      | arreglo   | Los modificadores del producto.                                               |
| `image_url`        | cadena    | La imagen principal del producto.                                             |
| `meta_title`       | cadena    | El nombre a usar en SEO.                                                      |
| `meta_description` | cadena    | La descripción a usar en SEO.                                                 |
| `tags`             | arreglo   | Los Tags asociados al producto.                                               |
| `vendor`           | arreglo   | El [Vendedor](/ayuda/desarrolladores/api/v1/vendedores) asociado al producto. |
| `skus[]`           | arreglo   | Los [Skus](/ayuda/desarrolladores/api/v1/skus) asociados al producto.         |
| `images[]`         | arreglo   | Todas las imágenes asociadas al producto.                                     |
| `is_active`        | booleano  | Si el producto está activo para venta.                                        |
| `available_at`     | timestamp | Fecha desde el día que está disponible el producto.                           |
| `created_at`       | timestamp | Fecha de creación del producto.                                               |
| `updated_at`       | timestamp | Última fecha de actualización del producto.                                   |

---

<a name="consultar-todos-los-productos"></a>
## Consultar todos los Productos

```
GET /v1/products
```

```json
{
  "data": [
    {
      "id": "prd_cifsjlwr60000gkyuc1vpvhkr",
      "object": "product",
      "permalink": "estampas",
      "name": "Estampas",
      "excerpt": null,
      "description": "<h2>Estampas de shoperti :)<\/h2>\r\n<p>La primer versi\u00f3n de las estampas de shoperti.<\/p>",
      "price": 2000,
      "compared_price": 0,
      "modifiers": [
        "Tama\u00f1o"
      ],
      "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
      "meta_title": "Estampas",
      "meta_description": null,
      "tags": [
        {
          "id": "tag_ciyf85gjg000080047ijf56h5",
          "object": "tag",
          "permalink": "nuevo",
          "title": "nuevo",
          "created_at": null,
          "updated_at": null
        }
      ],
      "vendor": {
        "id": "vnd_ciynguaqb0000jy0467ks30hq",
        "object": "vendor",
        "permalink": "shoperti",
        "name": "Shoperti",
        "description": null,
        "created_at": 1445261371,
        "updated_at": 1459212665
      },
      "skus": [
        {
          "id": "sku_cifsjlwrf0001gkyufmboq5sa",
          "object": "sku",
          "permalink": "3x3",
          "name": "3x3",
          "code": "1",
          "price": 2000,
          "compared_price": 0,
          "modifiers": [
            "3x3"
          ],
          "is_taxable": true,
          "in_stock": 0,
          "is_backorderable": false,
          "is_shipping_required": false,
          "is_notify": true,
          "stock_policy": "overall",
          "low_threshold": 2,
          "weight": null,
          "weight_unit": "kg",
          "position": 1,
          "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
          "created_at": 1444914676,
          "updated_at": 1453922774
        },
        {
          "id": "sku_cifya0sgi0000rryuxand3hga",
          "object": "sku",
          "permalink": "4x4",
          "name": "4x4",
          "code": "2",
          "price": 2000,
          "compared_price": 0,
          "modifiers": [
            "4x4"
          ],
          "is_taxable": true,
          "in_stock": 10,
          "is_backorderable": false,
          "is_shipping_required": false,
          "is_notify": null,
          "stock_policy": "overall",
          "low_threshold": 0,
          "weight": null,
          "weight_unit": "kg",
          "position": 1,
          "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
          "created_at": 1445261371,
          "updated_at": 1459212665
        }
      ],
      "images": [
        {
          "id": "fil_cifsjmerz0000ggyuk84rt0bm",
          "object": "file",
          "filename": "estampas.png",
          "original_filename": "shoperti-sin-slogan.png",
          "src": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png",
          "url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
          "mime_type": "image\/png",
          "size": 44526,
          "created_at": 1444914699,
          "updated_at": 1444914699
        }
      ],
      "is_active": true,
      "available_at": 1453929900,
      "created_at": 1444914676,
      "updated_at": 1471641724
    }
  ]
}
```

#### Parámetros

| Nombre       | Tipo     | Default | Requerido | Descripción                                                                                                            |
|--------------|--------- |---------|-----------|------------------------------------------------------------------------------------------------------------------------|
| `page`       | entero   | 1       | false     | Número de pagina a consultar.                                                                                          |
| `per_page`   | entero   | 50      | false     | La cantidad de resultados a mostrar.                                                                                   |
| `permalink`  | cadena   |         | false     | Filtrar permalinks separados por `,`                                                                                   |
| `id`         | cadena   |         | false     | Filtrar IDs separados por `,`.                                                                                         |
| `active`     | booleano |         | false     | Filtrar productos activos o inactivos                                                                                  |
| `published`  | booleano |         | false     | Filtrar productos publicados o no.                                                                                     |
| `listable`   | booleano |         | false     | Mostrar cada SKU listable de los productos.                                                                            |
| `price[min]` | cadena   |         | false     | Filtrar productos por precio mínimo.                                                                                   |
| `price[max]` | cadena   |         | false     | Filtrar productos por precio máximo.                                                                                   |
| `options[x]` | arreglo  |         | false     | Filtrar productos con la opción `x` igual al valor indicado.                                                           |
| `q`          | cadena   |         | false     | Filtrar productos que contengan la información de búsqueda.                                                            |
| `sort_by`    | cadena   |         | false     | `name-ascending`, `name-descending`, `created-ascending`, `created-descending`, `price-ascending`, `price-descending`. |

_Nota: En API pública los siguientes filtros son forzados:_ `active=true` `published=true`

---

<a name="consultar-un-producto"></a>
## Consultar un Producto

```
GET /v1/products/{id}
```

```json
{
  "data": {
    "id": "prd_cifsjlwr60000gkyuc1vpvhkr",
    "object": "product",
    "permalink": "estampas",
    "name": "Estampas",
    "excerpt": null,
    "description": "<h2>Estampas de shoperti :)<\/h2>\r\n<p>La primer versi\u00f3n de las estampas de shoperti.<\/p>",
    "price": 2000,
    "compared_price": 0,
    "modifiers": [
      "Tama\u00f1o"
    ],
    "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
    "meta_title": "Estampas",
    "meta_description": null,
    "tags": [
      {
        "id": "tag_ciyf85gjg000080047ijf56h5",
        "object": "tag",
        "permalink": "nuevo",
        "title": "nuevo",
        "created_at": null,
        "updated_at": null
      }
    ],
    "vendor": {
      "id": "vnd_ciynguaqb0000jy0467ks30hq",
      "object": "vendor",
      "permalink": "shoperti",
      "name": "Shoperti",
      "description": null,
      "created_at": 1445261371,
      "updated_at": 1459212665
    },
    "skus": [
      {
        "id": "sku_cifsjlwrf0001gkyufmboq5sa",
        "object": "sku",
        "permalink": "3x3",
        "name": "3x3",
        "code": "1",
        "price": 2000,
        "compared_price": 0,
        "modifiers": [
          "3x3"
        ],
        "is_taxable": true,
        "in_stock": 0,
        "is_backorderable": false,
        "is_shipping_required": false,
        "is_notify": true,
        "stock_policy": "overall",
        "low_threshold": 2,
        "weight": null,
        "weight_unit": "kg",
        "position": 1,
        "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
        "created_at": 1444914676,
        "updated_at": 1453922774
      },
      {
        "id": "sku_cifya0sgi0000rryuxand3hga",
        "object": "sku",
        "name": "4x4",
        "permalink": "4x4",
        "code": "2",
        "price": 2000,
        "compared_price": 0,
        "modifiers": [
          "4x4"
        ],
        "is_taxable": true,
        "in_stock": 10,
        "is_backorderable": false,
        "is_shipping_required": false,
        "is_notify": null,
        "stock_policy": "overall",
        "low_threshold": 0,
        "weight": null,
        "weight_unit": "kg",
        "position": 1,
        "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
        "created_at": 1445261371,
        "updated_at": 1459212665
      }
    ],
    "images": [
      {
        "id": "fil_cifsjmerz0000ggyuk84rt0bm",
        "object": "file",
        "filename": "estampas.png",
        "original_filename": "shoperti-sin-slogan.png",
        "src": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png",
        "url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
        "mime_type": "image\/png",
        "size": 44526,
        "created_at": 1444914699,
        "updated_at": 1444914699
      }
    ],
    "is_active": true,
    "available_at": 1453929900,
    "created_at": 1444914676,
    "updated_at": 1471641724
  }
}
```

#### Parámetros

Ningúno.

---

<a name="crear-un-producto"></a>
## Crear un Producto

```
POST /v1/products
```

#### Carga útil

Un objecto con los siguientes elementos:

| Nombre             | Tipo      | Requerido | Descripión                                                                    |
|--------------------|-----------|-----------|-------------------------------------------------------------------------------|
| `permalink`        | cadena    | false     | El permalink único del producto.                                              |
| `name`             | cadena    | true      | El nombre del producto.                                                       |
| `excerpt`          | cadena    | false     | Una descripción corta sobre el producto.                                      |
| `description`      | cadena    | false     | Descripción completa del producto.                                            |
| `modifiers[]`      | arreglo   | false     | Los modificadores del producto.                                               |
| `meta_title`       | cadena    | false     | El nombre a usar en SEO.                                                      |
| `meta_description` | cadena    | false     | La descripción a usar en SEO.                                                 |
| `tags`             | arreglo   | false     | Los Tags asociados al producto.                                               |
| `vendor`           | arreglo   | false     | El [Vendedor](/ayuda/desarrolladores/api/v1/vendedores) asociado al producto. |
| `skus[]`           | arreglo   | false     | Los [Skus](/ayuda/desarrolladores/api/v1/skus) asociados al producto.         |
| `images[]`         | arreglo   | false     | Todas las imágenes asociadas al producto.                                     |
| `is_active`        | booleano  | false     | Si el producto está activo para venta.                                        |
| `available_at`     | timestamp | false     | Fecha desde el día que está disponible el producto.                           |

Cada entrada en el arreglo de imágenes debe ser un objeto con alguna de las siguientes estructuras:
```json
{"id": "id_de_la_imagen"}
```
```json
{"filename": "nombre_de_la_imagen"}
```
```json
{"url": "url_donde_se_encuentra_la_imagen"}
```

Si es exitoso la respuesta será un objeto de `producto`.

#### Ejemplos

Crear un producto con una variante y precio.
```json
{
  "name": "Estampas",
  "description": "Estampas de excelente calidad",
  "tags": ["estampas"],
  "skus": [
    {
      "price": 10000 // en centavos
    }
  ]
}
```

Crear un producto con multiples variantes.
```json
{
  "name": "Estampas",
  "description": "Estampas de excelente calidad",
  "modifiers": ["Talla"],
  "skus": [
    {
      "modifiers": {"talla": "Chica"},
      "price": 10000,
      "code": "SKU-ESTAMPA-CHICA"
    },
    {
      "modifiers": {"talla": "Grande"},
      "price": 20000,
      "code": "SKU-ESTAMPA-GRANDE"
    }
  ]
}
```

Crear un producto con una variante, precio e imágenes.
```json
{
  "name": "Estampas",
  "description": "Estampas de excelente calidad",
  "tags": ["estampas"],
  "skus": [
    {
      "price": 10000 // en centavos
    }
  ],
  "images": [
     {
       "id": "fil_cifsjmerz0000ggyuk84rt0bm"
     },
     {
       "filename": "estampas.png", // Debe de existir como archivo en la plataforma
     },
     {
       "url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png"
     }
  ]
}
```

---

<a name="actualizar-un-producto"></a>
## Actualizar un Producto

```
POST /v1/products/{id}
```

#### Carga útil

Un objecto con los siguientes elementos:

| Nombre             | Tipo      | Requerido | Descripión                                                                    |
|--------------------|-----------|-----------|-------------------------------------------------------------------------------|
| `permalink`        | cadena    | false     | El permalink único del producto.                                              |
| `name`             | cadena    | true      | El nombre del producto.                                                       |
| `excerpt`          | cadena    | false     | Una descripción corta sobre el producto.                                      |
| `description`      | cadena    | false     | Descripción completa del producto.                                            |
| `modifiers[]`      | arreglo   | false     | Los modificadores del producto.                                               |
| `meta_title`       | cadena    | false     | El nombre a usar en SEO.                                                      |
| `meta_description` | cadena    | false     | La descripción a usar en SEO.                                                 |
| `tags`             | arreglo   | false     | Los Tags asociados al producto.                                               |
| `vendor`           | arreglo   | false     | El [Vendedor](/ayuda/desarrolladores/api/v1/vendedores) asociado al producto. |
| `skus[]`           | arreglo   | false     | Los [Skus](/ayuda/desarrolladores/api/v1/skus) asociados al producto.         |
| `images[]`         | arreglo   | false     | Todas las imágenes asociadas al producto.                                     |
| `is_active`        | booleano  | false     | Si el producto está activo para venta.                                        |
| `available_at`     | timestamp | false     | Fecha desde el día que está disponible el producto.                           |

Cada entrada en el arreglo de imágenes debe ser un objeto con alguna de las siguientes estructuras:
```json
{"id": "id_de_la_imagen"}
```
```json
{"filename": "nombre_de_la_imagen"}
```
```json
{"url": "url_donde_se_encuentra_la_imagen"}
```

Si es exitoso la respuesta será un objeto de `producto`.

#### Ejemplos

Actualizar la descripción de un producto.
```json
{
  "description": "Estampas de excelente calidad"
}
```

Actualizar un producto y uno de sus skus.
```json
{
  "name": "Nuevas nombre de producto",
  "skus": [
     {
        "id": "sku_cifsjlwrf0001gkyufmboq5sa",
        "price": 20000,
        "code": "NEW-CODE"
     },
     {
        "id": "sku_cifya0sgi0000rryuxand3hga"
     }
  ]
}
```

---

<a name="consultar-categorias-de-un-producto"></a>
## Consultar categorías de un producto

```
GET /v1/products/{id}/categories
```
```json
{
  "data": [
    {
      "id": "cat_cj81wyfwn00003io2e8caujbu",
      "object": "category",
      "permalink": "jeans-basicos",
      "title": "jeans BÁSICOS",
      "order": 1,
      "parent_id": "cat_cj81wy7fn000044o27wrz43e4",
      "updated_at": 1506449206,
      "created_at": 1506449197
    },
    {
      "id": "cat_cj81wy7fn000044o27wrz43e4",
      "object": "category",
      "permalink": "jeans",
      "title": "Jeans",
      "order": 2,
      "parent_id": null,
      "updated_at": 1506451097,
      "created_at": 1506449186
    }
  ]
}
```

#### Parámetros

Ninguno.

---

<a name="agregar-categorias-a-un-producto"></a>
## Agregar categorías a un producto

```
POST /v1/products/{id}/categories
```

#### Carga útil

Un arreglo con los IDs de las categorías a asociar.

Si es exitoso la respuesta será un HTTP `204 No Content`.

---

<a name="eliminar-un-producto"></a>
## Eliminar un Producto

```
DELETE /v1/products/{id}
```

#### Parámetros

Ningúno.

Si es exitoso la respuesta será un HTTP `204 No Content`.
