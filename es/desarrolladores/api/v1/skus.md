- [Intro](#intro)
- [Objeto de Sku](#objeto-de-sku)
- [Consultar todos los Skus](#consultar-todos-los-skus)
- [Consultar un Sku](#consultar-un-sku)
- [Crear un Sku](#crear-un-sku)
- [Actualizar un Sku](#actualizar-un-sku)
- [Eliminar un Sku](#eliminar-un-sku)

***

<a name="intro"></a>
# Skus API

Skus representan el listado de skus en una tienda.

---

<a name="objeto-de-sku"></a>
## Objeto de Sku

| Atributo               | Tipo      | Descripión                                                               |
|------------------------|-----------|--------------------------------------------------------------------------|
| `id`                   | cadena    | Identificador único del sku.                                             |
| `object`               | cadena    | El nombre del tipo de objeto.                                            |
| `permalink`            | cadena    | El permalink único del sku.                                              |
| `name`                 | cadena    | El nombre del sku.                                                       |
| `code`                 | cadena    | El código del sku.                                                       |
| `price`                | entero    | El precio de venta del sku.                                              |
| `compared_price`       | entero    | Precio más alto para comparar con el precio de venta activo.             |
| `modifiers[]`          | arreglo   | Los modificadores del sku.                                               |
| `image_url`            | cadena    | La imagen principal del sku.                                             |
| `is_listable`          | booleano  | Indica si el sku será listable en la tienda.                             |
| `is_taxable`           | booleano  | Indica si al sku se le incluyen impuestos.                               |
| `is_shipping_required` | boleano   | Indica si al sku require envío.                                          |
| `stock_policy`         | cadena    | La estrategía de inventario de sku: `none` o `overall`.                  |
| `is_backorderable`     | booleano  | Si el sku se puede seguir vendiendo una vez que se acabe el inventario.  |
| `in_stock`             | entero    | La cantidad de skus en inventario.                                       |
| `is_notify`            | booleano  | Si el sku debe de avisar cuándo el inventario esté bajo.                 |
| `low_threshold`        | booleano  | La cantidad en la cual avisar cuándo el inventario esté bajo.            |
| `weight_unit`          | cadena    | La unidad de peso del sku.                                               |
| `weight`               | cadena    | El peso del sku.                                                         |
| `position`             | entero    | La posición en la que ordena el sku.                                     |
| `product_id`           | cadena    | El producto al que pertenece el sku.                                     |
| `created_at`           | timestamp | Fecha de creación del sku.                                               |
| `updated_at`           | timestamp | Última fecha de actualización del sku.                                   |

---

<a name="consultar-todos-los-skus"></a>
## Consultar todos los Skus

```
GET /v1/skus
```

```json
{
  "data": [
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
  ]
}
```

#### Parámetros

| Nombre       | Tipo     | Default | Requerido | Descripción                                                                                                            |
|--------------|----------|---------|-----------|------------------------------------------------------------------------------------------------------------------------|
| `page`       | entero   | 1       | false     | Número de pagina a consultar.                                                                                          |
| `per_page`   | entero   | 50      | false     | La cantidad de resultados a mostrar.                                                                                   |
| `permalink`  | cadena   |         | false     | Filtrar permalinks separados por `,`                                                                                   |
| `id`         | cadena   |         | false     | Filtrar IDs separados por `,`.                                                                                         |
| `active`     | booleano |         | false     | Filtrar skus de productos activos o inactivos                                                                          |
| `published`  | booleano |         | false     | Filtrar skus de productos publicados o no.                                                                             |
| `listable`   | booleano |         | false     | Filtrar skus listables o no.                                                                                           |
| `price[min]` | cadena   |         | false     | Filtrar skus por precio mínimo.                                                                                        |
| `price[max]` | cadena   |         | false     | Filtrar skus por precio máximo.                                                                                        |
| `options[x]` | arreglo  |         | false     | Filtrar skus con la opción `x` igual al valor indicado.                                                                |
| `q`          | cadena   |         | false     | Filtrar skus que contengan la información de búsqueda.                                                                 |
| `sort_by`    | cadena   |         | false     | `name-ascending`, `name-descending`, `created-ascending`, `created-descending`, `price-ascending`, `price-descending`. |

_Nota: En API pública los siguientes filtros son forzados:_ `active=true` `published=true`

---

<a name="consultar-un-sku"></a>
## Consultar un Sku

```
GET /v1/skus/{id}
```

```json
{
  "data": {
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
  }
}
```

#### Parámetros

Ningúno.

---

<a name="crear-un-sku"></a>
## Crear un Sku

```
POST /v1/skus
```

#### Carga útil

Un objecto con los siguientes elementos:

| Nombre                 | Tipo      | Requerido | Descripión                                                              |
|------------------------|-----------|-----------|-------------------------------------------------------------------------|
| `product_id`           | cadena    | true      | El id del producto al cual pertenece el sku.                            |
| `code`                 | cadena    | false     | El código del sku.                                                      |
| `price`                | entero    | false     | El precio de venta del sku.                                             |
| `compared_price`       | entero    | false     | Precio más alto para comparar con el precio de venta activo.            |
| `modifiers[]`          | objeto    | false     | Los modificadores del sku.                                              |
| `image`                | objeto    | false     | La imagen principal del sku.                                            |
| `is_listable`          | booleano  | false     | Indica si el sku será listable en la tienda.                            |
| `is_taxable`           | booleano  | false     | Indica si al sku se le incluyen impuestos.                              |
| `is_shipping_required` | boleano   | false     | Indica si al sku require envío.                                         |
| `stock_policy`         | cadena    | false     | La estrategía de inventario de sku: `none` o `overall`.                 |
| `is_backorderable`     | booleano  | false     | Si el sku se puede seguir vendiendo una vez que se acabe el inventario. |
| `in_stock`             | entero    | false     | La cantidad de skus en inventario.                                      |
| `is_notify`            | booleano  | false     | Si el sku debe de avisar cuándo el inventario esté bajo.                |
| `low_threshold`        | booleano  | false     | La cantidad en la cual avisar cuándo el inventario esté bajo.           |
| `weight_unit`          | cadena    | false     | La unidad de peso del sku.                                              |
| `weight`               | cadena    | false     | El peso del sku.                                                        |
| `position`             | entero    | false     | La posición en la que ordena el sku.                                    |

El objeto para definir la imagen del sku debe tener alguna de las siguientes estructuras:
```json
{"id": "id_de_la_imagen"}
```
```json
{"filename": "nombre_de_la_imagen"}
```
```json
{"url": "url_donde_se_encuentra_la_imagen"}
```

Si es exitoso la respuesta será un objeto de `sku`.

#### Ejemplos

Crear un sku de un producto con un modificador* y precio.
```json
{
  "product_id": "prd_cifsjlwr60000gkyuc1vpvhkr",
  "modifiers": {"color": "azul"},
  "price": 10000 // en centavos
}
```

Crear un sku de un producto con dos modificadores* y precio.
```json
{
  "product_id": "prd_cifsjlwr60000gkyuc1vpvhkr",
  "modifiers": {"color": "azul", "talla": "grande"},
  "price": 10000 // en centavos
}
```

* Los modificadores deben de existir previamente en el producto.

---

<a name="actualizar-un-sku"></a>
## Actualizar un Sku

```
POST /v1/skus/{id}
```

#### Carga útil

Un objecto con los siguientes elementos:

| Nombre                 | Tipo      | Requerido | Descripión                                                              |
|------------------------|-----------|-----------|-------------------------------------------------------------------------|
| `code`                 | cadena    | false     | El código del sku.                                                      |
| `price`                | entero    | false     | El precio de venta del sku.                                             |
| `compared_price`       | entero    | false     | Precio más alto para comparar con el precio de venta activo.            |
| `modifiers[]`          | objeto    | false     | Los modificadores del sku.                                              |
| `image`                | objeto    | false     | La imagen principal del sku.                                            |
| `is_listable`          | booleano  | false     | Indica si el sku será listable en la tienda.                            |
| `is_taxable`           | booleano  | false     | Indica si al sku se le incluyen impuestos.                              |
| `is_shipping_required` | boleano   | false     | Indica si al sku require envío.                                         |
| `stock_policy`         | cadena    | false     | La estrategía de inventario de sku: `none` o `overall`.                 |
| `is_backorderable`     | booleano  | false     | Si el sku se puede seguir vendiendo una vez que se acabe el inventario. |
| `in_stock`             | entero    | false     | La cantidad de skus en inventario.                                      |
| `is_notify`            | booleano  | false     | Si el sku debe de avisar cuándo el inventario esté bajo.                |
| `low_threshold`        | booleano  | false     | La cantidad en la cual avisar cuándo el inventario esté bajo.           |
| `weight_unit`          | cadena    | false     | La unidad de peso del sku.                                              |
| `weight`               | cadena    | false     | El peso del sku.                                                        |
| `position`             | entero    | false     | La posición en la que ordena el sku.                                    |

El objeto para definir la imagen del sku debe tener alguna de las siguientes estructuras:
```json
{"id": "id_de_la_imagen"}
```
```json
{"filename": "nombre_de_la_imagen"}
```
```json
{"url": "url_donde_se_encuentra_la_imagen"}
```

Si es exitoso la respuesta será un objeto de `sku`.

#### Ejemplos

Editar un sku de un producto con un modificador* y precio.
```json
{
  "modifiers": {"color": "azul"},
  "price": 10000 // en centavos
}
```

Editar un sku de un producto con dos modificadores* y precio.
```json
{
  "modifiers": {"color": "azul", "talla": "grande"},
  "price": 10000 // en centavos
}
```

* Los modificadores deben de existir previamente en el producto.

---

<a name="eliminar-un-sku"></a>
## Eliminar un Sku

```
DELETE /v1/sku/{id}
```

#### Parámetros

Ningúno.

Si es exitoso la respuesta será un HTTP `204 No Content`.
