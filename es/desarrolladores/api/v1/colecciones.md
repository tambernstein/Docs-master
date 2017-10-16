- [Intro](#intro)
- [Objeto de Colección](#objeto-de-coleccion)
- [Consultar todas las Colecciones](#consultar-todas-las-colecciones)
- [Consultar una Colección](#consultar-una-coleccion)
- [Consultar los Productos de una Colección](#consultar-los-productos-de-una-coleccion)
- [Crear una Colección](#crear-una-coleccion)
- [Actualizar una Colección](#actualizar-una-coleccion)
- [Eliminar una Colección](#eliminar-una-coleccion)

***

<a name="intro"></a>
# Colecciones API

Colecciones representan el listado de colección en una tienda.

---

<a name="objeto-de-coleccion"></a>
## Objeto de Colección

| Atributo           | Tipo      | Descripión                                                           |
|--------------------|-----------|----------------------------------------------------------------------|
| `id`               | cadena    | Identificador único de la colección.                                 |
| `object`           | cadena    | El nombre del tipo de objeto.                                        |
| `permalink`        | cadena    | El permalink único de la colección.                                  |
| `title`            | cadena    | El nombre de la colección.                                           |
| `description`      | cadena    | Descripción completa del colección.                                  |
| `meta_title`       | cadena    | El nombre a usar en SEO.                                             |
| `meta_description` | cadena    | La descripción a usar en SEO.                                        |
| `image_url`        | cadena    | La imagen principal de la colección.                                 |
| `kind`             | cadena    | El tipo de colección que es, puede ser `products` o `smart`.         |
| `sorting_rule`     | cadena    | La regla con la cual se ordenan los productos de la colección.       |
| `is_visible`       | booleano  | Si la colección puede ser visible para el ciente                     |
| `visible_at`       | timestamp | Fecha desde el día que estrá visible la colección.                   |
| `created_at`       | timestamp | Fecha de creación de la colección.                                   |
| `updated_at`       | timestamp | Última fecha de actualización de la colección.                       |

---

<a name="consultar-todas-las-colecciones"></a>
## Consultar todas las Colecciones

```
GET /v1/collections
```

```json
{
  "data": [
    {
      "id": "col_cius7w8fe0000y8rrrpncrspp",
      "object": "collection",
      "permalink": "lo-mas-pedido",
      "title": "Lo mas pedido",
      "description": "<p>Lo m\u00e1s pedido del a\u00f1o<\/p>",
      "meta_title": "Lo mas pedido",
      "meta_description": "Lo m\u00e1s pedido del a\u00f1o",
      "kind": "smart",
      "sorting_rule": "manual",
      "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/img_shoperti.png",
      "is_visible": true,
      "visible_at": 1478026920,
      "created_at": 1477564737,
      "updated_at": 1479505024
    },
    {
      "id": "col_citkh316v001wtlrrfr74ke3b",
      "object": "collection",
      "permalink": "inicio",
      "title": "Inicio",
      "description": "<p>Colección de inicio</p>",
      "meta_title": "Inicio",
      "meta_description": "Colección de inicio",
      "kind": "products",
      "sorting_rule": "name-desc",
      "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/img_shoperti.png",
      "is_visible": true,
      "visible_at": 1474948800,
      "created_at": 1474919659,
      "updated_at": 1475035548
    }
  ]
}
```

#### Parámetros

| Nombre     | Tipo   | Default | Requerido | Descripción                          |
|------------|--------|---------|-----------|--------------------------------------|
| `page`     | entero | 1       | false     | Número de pagina a consultar.        |
| `per_page` | entero | 50      | false     | La cantidad de resultados a mostrar. |

---

<a name="consultar-una-coleccion"></a>
## Consultar una Colección

```
GET /v1/collections/{id}
```

```json
{
  "data": {
    "id": "col_cius7w8fe0000y8rrrpncrspp",
    "object": "collection",
    "permalink": "lo-mas-pedido",
    "title": "Lo mas pedido",
    "description": "<p>Lo m\u00e1s pedido del a\u00f1o<\/p>",
    "meta_title": "Lo mas pedido",
    "meta_description": "Lo m\u00e1s pedido del a\u00f1o",
    "kind": "smart",
    "sorting_rule": "manual",
    "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/img_shoperti.png",
    "is_visible": true,
    "visible_at": 1478026920,
    "created_at": 1477564737,
    "updated_at": 1479505024
  }
}
```

#### Parámetros

Ningúno.

---

<a name="consultar-los-productos-de-una-coleccion"></a>
## Consultar los Productos de una Colección

```
GET /v1/collections/{id}/products
```

```json
{
  "meta": {
    "pagination": {
      "current_page": 1,
      "previous_page": null,
      "next_page": null,
      "per_page": 50,
      "from": 1,
      "to": 2,
      "total_pages": 1,
      "total_items": 2,
      "links": {
        "previous_page": null,
        "next_page": null
      }
    }
  },
  "data": [
    {
      "id": "prd_cj81x4sbv000aico2facpvu6c",
      "object": "product",
      "permalink": "basic-jeans",
      "name": "Basic Jeans - hombre",
      "excerpt": "Jeans de corte recto",
      "description": "<p>Jeans modernos de corte recto que proyectan seriedad e informalidad</p>",
      "modifiers": null,
      "meta_title": "Jeans de corte recto",
      "meta_description": "basic jeans description",
      "meta_keywords": null,
      "vendor": {
        "id": "vnd_cj2cpmmpf000ab0o2h06b77b1",
        "object": "vendor",
        "permalink": "revi-s",
        "name": "Revi's",
        "description": null,
        "created_at": 1494041322,
        "updated_at": 1494041322
      },
      "tags": [
        {
          "id": "tag_cj81x4s5e0003ico29r8mok4q",
          "object": "tag",
          "permalink": "hombre",
          "title": "hombre",
          "created_at": 1506449493,
          "updated_at": 1506449493
        },
        {
          "id": "tag_cj81x4sci000bico28op0f9sr",
          "object": "tag",
          "permalink": "jeans",
          "title": "jeans",
          "created_at": 1506449493,
          "updated_at": 1506449493
        }
      ],
      "sku_id": "sku_cj81x4sds000eico2p3nqpldz",
      "skus": [
        {
          "id": "sku_cj81x4sds000eico2p3nqpldz",
          "object": "sku",
          "permalink": "default",
          "name": "Default",
          "code": null,
          "price": 50000,
          "compared_price": 0,
          "modifiers": null,
          "is_listable": true,
          "is_taxable": true,
          "is_shipping_required": false,
          "stock_policy": "none",
          "is_backorderable": false,
          "in_stock": null,
          "low_threshold": null,
          "weight_unit": "kg",
          "weight_source": null,
          "weight": null,
          "position": 1,
          "product_id": "prd_cj81x4sbv000aico2facpvu6c",
          "created_at": 1506449493,
          "updated_at": 1506539847,
          "image_url": null
        }
      ],
      "images": [],
      "available_at": 1504288440,
      "created_at": 1506449493,
      "updated_at": 1506647256,
      "price": 50000,
      "compared_price": 0,
      "image_url": null
    },
    {
      "id": "prd_cj81x4s3y0001ico2we5lbv7n",
      "object": "product",
      "permalink": "camisa-manga-larga",
      "name": "Camisa Manga Larga",
      "excerpt": "Camisa manga larga casual",
      "description": "<p>Obtén la imagen que buscas con esta camisa de manga larga de estilo casual</p>",
      "modifiers": [
        "color",
        "tamaño"
      ],
      "meta_title": "Camisa manga larga",
      "meta_description": "Camisa manga larga casual",
      "meta_keywords": null,
      "vendor": {
        "id": "vnd_cj2cpmmj10002b0o27uta19d4",
        "object": "vendor",
        "permalink": "hollyshirts",
        "name": "HollyShirts",
        "description": null,
        "created_at": 1494041322,
        "updated_at": 1494041322
      },
      "tags": [
        {
          "id": "tag_cj81x4s510002ico289blufka",
          "object": "tag",
          "permalink": "camisa",
          "title": "camisa",
          "created_at": 1506449493,
          "updated_at": 1506449493
        }
      ],
      "sku_id": "sku_cj81x4s750006ico2sovn9mrf",
      "skus": [
        {
          "id": "sku_cj81x4s750006ico2sovn9mrf",
          "object": "sku",
          "permalink": "rojo-chico",
          "name": "rojo / chico",
          "code": "TSHR1",
          "price": 45000,
          "compared_price": 52000,
          "modifiers": [
            "rojo",
            "chico"
          ],
          "is_listable": false,
          "is_taxable": true,
          "is_shipping_required": true,
          "stock_policy": "overall",
          "is_backorderable": true,
          "in_stock": 100,
          "low_threshold": 10,
          "weight_unit": "gr",
          "weight_source": 300,
          "weight": 300,
          "position": 1,
          "product_id": "prd_cj81x4s3y0001ico2we5lbv7n",
          "created_at": 1506449493,
          "updated_at": 1506449493,
          "image_url": null
        }
      ],
      "images": [],
      "available_at": 1504573620,
      "created_at": 1506449493,
      "updated_at": 1506647278,
      "price": 45000,
      "compared_price": 52000,
      "image_url": null
    }
  ]
}
```

#### Parámetros

| Nombre       | Tipo     | Default | Requerido | Descripción                                                                                                            |
|--------------|----------|---------|-----------|------------------------------------------------------------------------------------------------------------------------|
| `page`       | entero   | 1       | false     | Número de pagina a consultar.                                                                                          |
| `per_page`   | entero   | 50      | false     | La cantidad de resultados a mostrar.                                                                                   |
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

<a name="crear-una-coleccion"></a>
## Crear una Colección

```
POST /v1/collections
```

#### Parámetros

| Nombre              | Tipo      | Requerido | Descripión                                                     |
|-------------------- |-----------|-----------|----------------------------------------------------------------|
| `title`             | cadena    | true      | El nombre de la colección.                                     |
| `description`       | cadena    | false     | Descripción completa del colección.                            |
| `meta_title`        | cadena    | false     | El nombre a usar en SEO.                                       |
| `meta_description`  | cadena    | false     | La descripción a usar en SEO.                                  |
| `image_url`         | cadena    | false     | La imagen principal de la colección.                           |
| `kind`              | cadena    | true      | El tipo de colección que es, puede ser `products` o `smart`.   |
| `sorting_rule`      | cadena    | false     | La regla con la cual se ordenan los productos de la colección. |
| `is_visible`        | booleano  | false     | Si la colección puede ser visible para el ciente               |
| `visible_at`        | timestamp | false     | Fecha desde el día que estrá visible la colección.             |

Si es exitoso la respuesta será un objeto de `colección`.

---

<a name="actualizar-una-coleccion"></a>
## Actualizar una Colección

```
POST /v1/collections/{id}
```

#### Parámetros

| Nombre              | Tipo      | Requerido | Descripión                                                     |
|-------------------- |-----------|-----------|----------------------------------------------------------------|
| `title`             | cadena    | true      | El nombre de la colección.                                     |
| `description`       | cadena    | false     | Descripción completa del colección.                            |
| `meta_title`        | cadena    | false     | El nombre a usar en SEO.                                       |
| `meta_description`  | cadena    | false     | La descripción a usar en SEO.                                  |
| `image_url`         | cadena    | false     | La imagen principal de la colección.                           |
| `kind`              | cadena    | true      | El tipo de colección que es, puede ser `products` o `smart`.   |
| `sorting_rule`      | cadena    | false     | La regla con la cual se ordenan los productos de la colección. |
| `is_visible`        | booleano  | false     | Si la colección puede ser visible para el ciente               |
| `visible_at`        | timestamp | false     | Fecha desde el día que estrá visible la colección.             |

Si es exitoso la respuesta será un objeto de `colección`.

---

<a name="eliminar-una-coleccion"></a>
## Eliminar una Colección

```
DELETE /v1/collections/{id}
```

#### Parámetros

Ningúno.

Si es exitoso la respuesta será un HTTP `204 No Content`.

