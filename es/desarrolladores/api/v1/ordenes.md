- [Intro](#intro)
- [Objeto de Orden](#objeto-de-orden)
- [Consultar todas las Órdenes](#consultar-todas-las-ordenes)
- [Consultar una Orden](#consultar-una-orden)

***

<a name="intro"></a>
# Órdenes API

Órdenes representan el listado de orden en una tienda.

---

<a name="objeto-de-orden"></a>
## Objeto de Orden

| Atributo               | Tipo      | Descripión                                                             |
|------------------------|-----------|------------------------------------------------------------------------|
| `id`                   | cadena    | Identificador único de la orden.                                       |
| `object`               | cadena    | El nombre del tipo de objeto.                                          |
| `number`               | cadena    | El number único de la orden.                                           |
| `status`               | cadena    | El estado actual de la orden.                                          |
| `financial_status`     | cadena    | El estado actual del pago de la orden.                                 |
| `fulfillment_status`   | cadena    | El estado actual del envío de la orden.                                |
| `email`                | cadena    | El correo electrónico asociado con la orden.                           |
| `items`                | arreglo   | Los productos relacionados con la orden.                               |
| `is_shipping_required` | boleano   | Indica si la orden debe de ser envíada.                                |
| `shipping_lines`       | arreglo   | El método de envío elegido al momento de checkout por el cliente.      |
| `shipping_rate`        | entero    | La cantidad pagada por el envío de la orden.                           |
| `shipping`             | arreglo   | La dirección de envío de la orden.                                     |
| `billing`              | arreglo   | La dirección de pago de la orden.                                      |
| `discount_codes`       | arreglo   | Los códigos de descuento usados en la orden.                           |
| `is_gift`              | boleano   | Indica si la orden fue marcada como regalo.                            |
| `gift_message`         | cadena    | El mensaje de regalo de la orden.                                      |
| `source_name`          | cadena    | El medio por el cual fue creada la orden.                              |
| `customer_note`        | cadena    | La nota agregada por el cliente a la orden.                            |
| `cancel_reason`        | cadena    | Razón por la cual fue cancelada la orden.                              |
| `browser_ip`           | cadena    | IP desde donde se creó la orden.                                       |
| `user_agent`           | cadena    | Información sobre el cliente o navegador desde donde se creo la orden. |
| `landing_site`         | cadena    | Página desde dónde se creo la órden.                                   |
| `referring_site`       | cadena    | Página desde dónde visito el cliente antes de crear la orden.          |
| `gateway`              | cadena    | Procesador de pago usado al pagar la orden.                            |
| `total_products`       | entero    | Cantidad total de productos en la orden.                               |
| `total_discount`       | entero    | Cantidad total de descuento en la orden.                               |
| `total_items`          | entero    | Cantidad total de productos y su cantidad en la orden.                 |
| `total_items_price`    | entero    | Suma total de precio de los productos en la orden.                     |
| `subtotal_price`       | entero    | Subtotal de la orden.                                                  |
| `total_taxes`          | entero    | Cantidad total de impuestos de la orden.                               |
| `total_price`          | entero    | Total de la orden.                                                     |
| `currency`             | cadena    | Moneda en la cual fue pagada la orden.                                 |
| `total_weight`         | entero    | Total de peso de los productos en la orden.                            |
| `transactions`         | arreglo   | La lista de transaciones procesadas en la orden.                       |
| `is_test`              | boleano   | Indica si la orden fue creada en modo de prueba.                       |
| `customer_id`          | cadena    | ID único del cliente que creó la orden.                                |
| `channel_id`           | cadena    | ID único del canal en cual fue creadad la orden.                       |
| `cart_id`              | cadena    | ID único del carrito del cual se creó la orden.                        |
| `canceler_id`          | cadena    | ID único del usuario que canceló la orden.                             |
| `placed_at`            | timestamp | Fecha en la cual fue colocada la orden.                                |
| `archived_at`          | timestamp | Fecha en la cual fue archivada la orden.                               |
| `canceled_at`          | timestamp | Fecha en la cual fue cancelada la orden.                               |
| `created_at`           | timestamp | Fecha de creación de la orden.                                         |
| `updated_at`           | timestamp | Última fecha de actualización de la orden.                             |

---

<a name="consultar-todas-las-ordenes"></a>
## Consultar todas las Ordenes

```
GET /v1/orders
```

```json
{
  "data": [
    {
      "id": "ord_cix9i2dss0000ro0412gpstv4",
      "object": "order",
      "number": "13",
      "status": "placed",
      "financial_status": "paid",
      "fulfillment_status": "unfulfilled",
      "email": "joe@example.com",
      "items": [
        {
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
        },
        {
          "id": "itm_cix9i2dvb0002ro04xm3368lh",
          "object": "order_item",
          "permalink": "laptop-backpack",
          "name": "Laptop Backpack Verde \/ M",
          "product_name": "Laptop Backpack",
          "sku_name": "Verde \/ M",
          "vendor": null,
          "code": "",
          "image": null,
          "price": 10000,
          "compared_price": 0,
          "quantity": 1,
          "discount": null,
          "is_taxable": false,
          "tax_rate": 0,
          "total": 10000,
          "fulfilled": 0,
          "is_shipping_required": true,
          "weight": 1000,
          "stock_id": null,
          "order_id": "ord_cix9i2dss0000ro0412gpstv4",
          "product_id": "prd_ciwlp5ltj0000vj044km043on",
          "sku_id": "sku_ciwlp5luz0001vj042jge077p",
          "created_at": 1482963310,
          "updated_at": 1483039926
        }
      ],
      "is_shipping_required": true,
      "shipping_lines": {
        "id": "shr_ciwloy3z9002wvj0415s2gp3n",
        "kind": "weight",
        "price": 10000,
        "source": "platform",
        "title": "Env\u00edo est\u00e1ndar",
        "reference": "Env\u00edo est\u00e1ndar"
      },
      "shipping_rate": 10000,
      "shipping": {
        "address": {
          "city": "Mexico",
          "country": "Mexico",
          "country_code": "MX",
          "address1": "Calle Hamburgo #218",
          "address2": "Roma Norte",
          "postcode": "06600",
          "state": "Ciudad de M\u00e9xico",
          "state_code": "DF"
        },
        "name": "Juan Tremendo",
        "phone": "5521231637"
      },
      "billing": {
        "address": {
          "city": "Mexico",
          "country": "Mexico",
          "country_code": "MX",
          "address1": "Calle Hamburgo #218",
          "address2": "Roma Norte",
          "postcode": "06600",
          "state": "Ciudad de M\u00e9xico",
          "state_code": "DF"
        },
        "name": "Juan Tremendo",
        "phone": "5521231637"
      },
      "discount_codes": null,
      "is_gift": false,
      "gift_message": null,
      "source_name": "web",
      "customer_note": null,
      "order_note": null,
      "cancel_reason": null,
      "browser_ip": "127.0.0.1",
      "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_12_2) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/55.0.2883.95 Safari\/537.36",
      "landing_site": "http:\/\/mitienda.shoperti.com\/productos",
      "referring_site": "",
      "gateway": "conekta",
      "total_products": 2,
      "total_discount": 0,
      "total_items": 2,
      "total_items_price": 40000,
      "subtotal_price": 40000,
      "total_taxes": 0,
      "total_price": 50000,
      "currency": "MXN",
      "total_weight": 2000,
      "transactions": [
        {
          "id": "tra_cixarpesl00005004cpjqxuo2",
          "object": "transaction",
          "amount": 50000,
          "currency": "MXN",
          "authorization": "574462",
          "code": null,
          "reference": "586564dcc835f0b4f301c5b4",
          "gateway": "conekta",
          "source_name": "web",
          "kind": "charge",
          "status": "succeeded",
          "credit_card_number": null,
          "credit_card_brand": null,
          "message": "Transaction approved",
          "is_test": true,
          "order_id": "ord_cix9i2dss0000ro0412gpstv4",
          "parent_id": null,
          "created_at": 1483039967,
          "updated_at": 1483039967
        }
      ],
      "is_test": true,
      "customer_id": "cus_ciwmf6d720000vj0447vs29yu",
      "channel_id": "chn_ciwloy2690000vj040w8hxqap",
      "cart_id": "crt_cix05w6st0000uk047v34b42t",
      "canceler_id": null,
      "placed_at": 1483039967,
      "archived_at": null,
      "canceled_at": null,
      "created_at": 1482963310,
      "updated_at": 1483039967
    },
    {
      "id": "ord_cix04qsm80000cs047ovdgnkm",
      "object": "order",
      "number": "12",
      "status": "placed",
      "financial_status": "paid",
      "fulfillment_status": "fulfilled",
      "email": "joe@example.com",
      "items": [
        {
          "id": "itm_cix04qsn00002cs04y6zlnszw",
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
          "fulfilled": 1,
          "is_shipping_required": true,
          "weight": 1000,
          "stock_id": null,
          "order_id": "ord_cix04qsm80000cs047ovdgnkm",
          "product_id": "prd_ciwwv08oj00005c04m9tbysad",
          "sku_id": "sku_ciwwv08s500015c043okf1lay",
          "created_at": 1482396739,
          "updated_at": 1482397159
        }
      ],
      "is_shipping_required": true,
      "shipping_lines": {
        "id": "shr_ciwloy3z9002wvj0415s2gp3n",
        "kind": "weight",
        "price": 10000,
        "source": "platform",
        "title": "Env\u00edo est\u00e1ndar",
        "reference": "Env\u00edo est\u00e1ndar"
      },
      "shipping_rate": 10000,
      "shipping": {
        "address": {
          "city": "Mexico",
          "country": "Mexico",
          "country_code": "MX",
          "address1": "Calle Hamburgo #218",
          "address2": "Roma Norte",
          "postcode": "06600",
          "state": "Ciudad de M\u00e9xico",
          "state_code": "DF"
        },
        "name": "Juan Tremendo",
        "phone": "5522241607"
      },
      "billing": {
        "address": {
          "city": "Mexico",
          "country": "Mexico",
          "country_code": "MX",
          "address1": "Calle Hamburgo #218",
          "address2": "Roma Norte",
          "postcode": "06600",
          "state": "Ciudad de M\u00e9xico",
          "state_code": "DF"
        },
        "name": "Juan Tremendo",
        "phone": "5522241607"
      },
      "discount_codes": null,
      "is_gift": false,
      "gift_message": null,
      "source_name": "web",
      "customer_note": null,
      "order_note": null,
      "cancel_reason": null,
      "browser_ip": "127.0.0.1",
      "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_12_1) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/55.0.2883.95 Safari\/537.36",
      "landing_site": "http:\/\/mitienda.shoperti.com",
      "referring_site": "http:\/\/checkout.shoperti.com\/mitienda\/checkouts\/chk_cix042nt800015c049skwyfbv\/complete",
      "gateway": "manual",
      "total_products": 1,
      "total_discount": 0,
      "total_items": 1,
      "total_items_price": 30000,
      "subtotal_price": 30000,
      "total_taxes": 0,
      "total_price": 40000,
      "currency": "MXN",
      "total_weight": 1000,
      "transactions": [
        {
          "id": "tra_cix04wfho0000uk04qskjxand",
          "object": "transaction",
          "amount": 40000,
          "currency": "MXN",
          "authorization": null,
          "code": null,
          "reference": null,
          "gateway": "manual",
          "source_name": "web",
          "kind": "charge",
          "status": "succeeded",
          "credit_card_number": null,
          "credit_card_brand": null,
          "message": null,
          "is_test": false,
          "order_id": "ord_cix04qsm80000cs047ovdgnkm",
          "parent_id": "tra_cix04r4780000cs04mm6ikee5",
          "created_at": 1482397002,
          "updated_at": 1482397002
        },
        {
          "id": "tra_cix04r4780000cs04mm6ikee5",
          "object": "transaction",
          "amount": 40000,
          "currency": "MXN",
          "authorization": null,
          "code": null,
          "reference": null,
          "gateway": "manual",
          "source_name": "web",
          "kind": "charge",
          "status": "pending",
          "credit_card_number": null,
          "credit_card_brand": null,
          "message": null,
          "is_test": false,
          "order_id": "ord_cix04qsm80000cs047ovdgnkm",
          "parent_id": null,
          "created_at": 1482396754,
          "updated_at": 1482396754
        }
      ],
      "is_test": false,
      "customer_id": "cus_ciwmf6d720000vj0447vs29yu",
      "channel_id": "chn_ciwloy2690000vj040w8hxqap",
      "cart_id": "crt_cix04qlxn0000cs04c9j2pv2o",
      "canceler_id": null,
      "placed_at": 1482396754,
      "archived_at": null,
      "canceled_at": null,
      "created_at": 1482396739,
      "updated_at": 1482397159
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

<a name="consultar-una-orden"></a>
## Consultar una Orden

```
GET /v1/orders/{id}
```

```json
{
  "data": {
    "id": "ord_cix9i2dss0000ro0412gpstv4",
    "object": "order",
    "number": "13",
    "status": "placed",
    "financial_status": "paid",
    "fulfillment_status": "unfulfilled",
    "email": "joe@example.com",
    "items": [
      {
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
      },
      {
        "id": "itm_cix9i2dvb0002ro04xm3368lh",
        "object": "order_item",
        "permalink": "laptop-backpack",
        "name": "Laptop Backpack Verde \/ M",
        "product_name": "Laptop Backpack",
        "sku_name": "Verde \/ M",
        "vendor": null,
        "code": "",
        "image": null,
        "price": 10000,
        "compared_price": 0,
        "quantity": 1,
        "discount": null,
        "is_taxable": false,
        "tax_rate": 0,
        "total": 10000,
        "fulfilled": 0,
        "is_shipping_required": true,
        "weight": 1000,
        "stock_id": null,
        "order_id": "ord_cix9i2dss0000ro0412gpstv4",
        "product_id": "prd_ciwlp5ltj0000vj044km043on",
        "sku_id": "sku_ciwlp5luz0001vj042jge077p",
        "created_at": 1482963310,
        "updated_at": 1483039926
      }
    ],
    "is_shipping_required": true,
    "shipping_lines": {
      "id": "shr_ciwloy3z9002wvj0415s2gp3n",
      "kind": "weight",
      "price": 10000,
      "source": "platform",
      "title": "Env\u00edo est\u00e1ndar",
      "reference": "Env\u00edo est\u00e1ndar"
    },
    "shipping_rate": 10000,
    "shipping": {
      "address": {
        "city": "Mexico",
        "country": "Mexico",
        "country_code": "MX",
        "address1": "Calle Hamburgo #218",
        "address2": "Roma Norte",
        "postcode": "06600",
        "state": "Ciudad de M\u00e9xico",
        "state_code": "DF"
      },
      "name": "Juan Tremendo",
      "phone": "5521231637"
    },
    "billing": {
      "address": {
        "city": "Mexico",
        "country": "Mexico",
        "country_code": "MX",
        "address1": "Calle Hamburgo #218",
        "address2": "Roma Norte",
        "postcode": "06600",
        "state": "Ciudad de M\u00e9xico",
        "state_code": "DF"
      },
      "name": "Juan Tremendo",
      "phone": "5521231637"
    },
    "discount_codes": null,
    "is_gift": false,
    "gift_message": null,
    "source_name": "web",
    "customer_note": null,
    "order_note": null,
    "cancel_reason": null,
    "browser_ip": "127.0.0.1",
    "user_agent": "Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_12_2) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/55.0.2883.95 Safari\/537.36",
    "landing_site": "http:\/\/mitienda.shoperti.com\/productos",
    "referring_site": "",
    "gateway": "conekta",
    "total_products": 2,
    "total_discount": 0,
    "total_items": 2,
    "total_items_price": 40000,
    "subtotal_price": 40000,
    "total_taxes": 0,
    "total_price": 50000,
    "currency": "MXN",
    "total_weight": 2000,
    "transactions": [
      {
        "id": "tra_cixarpesl00005004cpjqxuo2",
        "object": "transaction",
        "amount": 50000,
        "currency": "MXN",
        "authorization": "574462",
        "code": null,
        "reference": "586564dcc835f0b4f301c5b4",
        "gateway": "conekta",
        "source_name": "web",
        "kind": "charge",
        "status": "succeeded",
        "credit_card_number": null,
        "credit_card_brand": null,
        "message": "Transaction approved",
        "is_test": true,
        "order_id": "ord_cix9i2dss0000ro0412gpstv4",
        "parent_id": null,
        "created_at": 1483039967,
        "updated_at": 1483039967
      }
    ],
    "is_test": true,
    "customer_id": "cus_ciwmf6d720000vj0447vs29yu",
    "channel_id": "chn_ciwloy2690000vj040w8hxqap",
    "cart_id": "crt_cix05w6st0000uk047v34b42t",
    "canceler_id": null,
    "placed_at": 1483039967,
    "archived_at": null,
    "canceled_at": null,
    "created_at": 1482963310,
    "updated_at": 1483039967
  }
}
```

#### Parámetros

Ningúno.

