- [Intro](#intro)
- [Objeto de Envío](#objeto-de-envio)
- [Consultar todos los Envíos](#consultar-todos-los-envios)
- [Consultar un Envío](#consultar-un-envio)
- [Crear un Envío](#crear-un-envio)
- [Actualizar un Envío](#actualizar-un-envio)
- [Cancelar un Envío](#cancelar-un-envio)

***

<a name="intro"></a>
# Envíos API

Envíos representan el listado de Envíos de una Órden en una tienda.

---

<a name="objeto-de-envio"></a>
## Objeto de Envío

| Atributo               | Tipo      | Descripión                                                           |
|------------------------|-----------|----------------------------------------------------------------------|
| `id`                   | cadena    | Identificador único del envío.                                       |
| `object`               | cadena    | El nombre del tipo de objeto.                                        |
| `kind`                 | cadena    | El tipo de envío: `parcial`o `full`.                                 |
| `status`               | cadena    | El estado del envío: `succeeded`, `canceled`, `pending`, `failed`.   |
| `items`                | arreglo   | Los productos que han sido envíados.                                 |
| `items_count`          | entero    | La cantidad de productos en el envío.                                |
| `tracking_code`        | cadena    | El código de envío.                                                  |
| `carrier`              | cadena    | Línea transportista del envío.                                       |
| `is_customer_notified` | booleano  | Si el cliente fue notificado sobre en envío.                         |
| `order_id`             | cadena    | El indentificador único de la órden al que pertenece el envío.       |
| `created_at`           | timestamp | Fecha de creación del envío.                                         |
| `updated_at`           | timestamp | Última fecha de actualización del envío.                             |

---

<a name="consultar-todos-los-envios"></a>
## Consultar todos los Envíos de una Órden

```
GET /v1/orders/{id}/fulfillments
```

```json
{
  "data": [
    { 
      "id": "ful_cj45tszoe00007z04qe1qcuwv",
      "object": "fulfillment",
      "kind": "full",
      "status": "succeeded",
      "items": [
        {
          "fulfilled_quantity": 1,
          "fulfilled_weight": 5000,
          "id": "itm_cix9i2dvi0003ro04r8d6xfp8",
          "object": "order_item",
          "permalink": "backpack",
          "name": "Backpack",
          "product_name": "Backpack",
          "sku_name": "",
          "vendor": null,
          "code": "",
          "image": null,
          "price": 30000,
          "compared_price": 0,
          "quantity": 1,
          "discount": null,
          "is_taxable": false,
          "tax_rate": 0,
          "total": 30000,
          "fulfilled": 0,
          "is_shipping_required": true,
          "weight": 1000,
          "stock_id": null,
          "order_id": "ord_cix9i2dss0000ro0412gpstv4",
          "product_id": "prd_ciwwv08oj00005c04m9tbysad",
          "sku_id": "sku_ciwwv08s500015c043okf1lay",
          "created_at": 1482963310,
          "updated_at": 1482963310
        }
      ],
      "items_count": 1,
      "tracking_code": "12345678",
      "carrier": "UPS",
      "is_customer_notified": true,
      "order_id": "ord_cix9i2dss0000ro0412gpstv4",
      "created_at": 1497978639,
      "updated_at": 1497978645
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

<a name="consultar-un-envio"></a>
## Consultar un Envío de una Órden

```
GET /v1/orders/{id}/fulfillments/{id}
```

```json
{
  "data": { 
    "id": "ful_cj45tszoe00007z04qe1qcuwv",
    "object": "fulfillment",
    "kind": "full",
    "status": "succeeded",
    "items": [
      {
        "fulfilled_quantity": 1,
        "fulfilled_weight": 5000,
        "id": "itm_cix9i2dvi0003ro04r8d6xfp8",
        "object": "order_item",
        "permalink": "backpack",
        "name": "Backpack",
        "product_name": "Backpack",
        "sku_name": "",
        "vendor": null,
        "code": "",
        "image": null,
        "price": 30000,
        "compared_price": 0,
        "quantity": 1,
        "discount": null,
        "is_taxable": false,
        "tax_rate": 0,
        "total": 30000,
        "fulfilled": 0,
        "is_shipping_required": true,
        "weight": 1000,
        "stock_id": null,
        "order_id": "ord_cix9i2dss0000ro0412gpstv4",
        "product_id": "prd_ciwwv08oj00005c04m9tbysad",
        "sku_id": "sku_ciwwv08s500015c043okf1lay",
        "created_at": 1482963310,
        "updated_at": 1482963310
      }
    ],
    "items_count": 1,
    "tracking_code": "12345678",
    "carrier": "UPS",
    "is_customer_notified": true,
    "order_id": "ord_cix9i2dss0000ro0412gpstv4",
    "created_at": 1497978639,
    "updated_at": 1497978645
  }
}
```

#### Parámetros

Ningúno.

---

<a name="crear-un-envio"></a>
## Crear un Envío para una Órden

```
POST /v1/orders/{id}/fulfillments
```

| Nombre                 | Tipo      | Requerido | Descripión                               |
|------------------------|-----------|-----------|------------------------------------------|
| `tracking_code`        | cadena    | false     | El codigo del envío.                     |
| `carrier`              | cadena    | false     | Línea transportista del envío.           |
| `is_customer_notified` | booleano  | false     | Notificar al cliente sobre el envío.     |
| `items[]`              | arreglo   | false     | Los productos a enviar.                  |

Si es exitoso la respuesta será un objeto de `envio`.

#### Ejemplos

Crear un envío con código de envío y línea transportista.
```json
{
  "tracking_code": "12345678",
  "carrier": "UPS",
  "items": [
    {
      "id": "itm_cix9i2dvi0003ro04r8d6xfp8"
    }
  ]
}
```

Crear un envío parcial.
```json
{
  "tracking_code": "12345678",
  "carrier": "UPS",
  "items": [
    {
      "id": "itm_cix9i2dvi0003ro04r8d6xfp8",
      "quantity": 1,
    }
  ]
}
```

---

<a name="actualizar-un-envio"></a>
## Actualizar un Envío para una Órden

```
POST /v1/orders/{id}/fulfillments/{id}
```

| Nombre                 | Tipo      | Requerido | Descripión                                   |
|------------------------|-----------|-----------|----------------------------------------------|
| `tracking_code`        | cadena    | false     | El codigo del envío.                         |
| `carrier`              | cadena    | false     | Línea transportista del envío.               |
| `is_customer_notified` | booleano  | false     | Notificar al cliente sobre el cambio envío.  |

Si es exitoso la respuesta será un objeto de `envio`.

---

<a name="cancelar-un-envio"></a>
## Cancelar un Envío

```
POST /v1/orders/{id}/fulfillments/{id}/cancel
```

#### Parámetros

Ningúno.

Si es exitoso la respuesta será un objeto de `envio`.

