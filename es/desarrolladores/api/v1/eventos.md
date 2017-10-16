- [Intro](#intro)
- [Objeto de Evento](#objeto-de-evento)
- [Tips de Evento](#tipos-de-evento)
- [Consultar todos los Eventos](#consultar-todos-los-eventos)
- [Consultar un Evento](#consultar-un-evento)

***

<a name="intro"></a>
# Eventos API

Los eventos son una forma de hacerte saber cuando algo interesante pasa en tu tienda. En el momento que un evento interesante ocurre, nosotros creamos un objeto `Evento` por ejemplo, cuando una orden fue pagada creamos un evento `order.paid`, cuando elimina un producto creamos un evento `product.deleted`.

Puedes consultar los eventos o un sólo evento via el API. También contamos con un sistema para notificarte cuando estos eventos suceden por medio de un sistema llamado [webhooks](/ayuda/desarrolladores/webhooks) para saber más, puedes [consultar nuestra guía](/ayuda/desarrolladores/webhooks).

> NOTA: Por el momento sólo garantizamos acceso a los eventos via el API por menos a 30 días.

---

<a name="objeto-de-evento"></a>
## Objeto de Evento

| Atributo           | Tipo      | Descripión                                                           |
|--------------------|-----------|----------------------------------------------------------------------|
| `id`               | cadena    | Identificador único del evento.                                      |
| `object`           | cadena    | El nombre del tipo de objeto.                                        |
| `kind`             | cadena    | El tipo de evento.                                                   |
| `data`             | cadena    | Datos relacionados con el evento.                                    |
| `pending_webhooks` | entero    | La cantidad de webhooks pendientes a notificar.                      |
| `created_at`       | timestamp | Fecha de creación del evento.                                        |
| `updated_at`       | timestamp | Última fecha de actualización del evento.                            |

---

<a name="tipos-de-evento"></a>
## Tipos de Evento

| Evento                | Objeto    | Descripión                                                          |
|-----------------------|-----------|---------------------------------------------------------------------|
| `collection.created`  | colección | Ocurre cuando una colección es creada.                              |
| `collection.deleted`  | colección | Ocurre cuando una colección es eliminada.                           |
| `collection.updated`  | colección | Ocurre cuando una colección es actualizada.                         |
| `customer.created`    | cliente   | Ocurre cuando un cliente es creado.                                 |
| `customer.created`    | cliente   | Ocurre cuando un cliente es actualizado.                            |
| `fulfillment.created` | envío     | Ocurre cuando un envío es creado.                                   |
| `fulfillment.updated` | envío     | Ocurre cuando un envío es actualizado.                              |
| `order.placed`        | orden     | Ocurre cuando una orden ha sido recibida.                           |
| `order.paid`          | orden     | Ocurre cuando una orden ha sido pagada.                             |
| `product.created`     | producto  | Ocurre cuando un producto es creado.                                |
| `product.deleted`     | producto  | Ocurre cuando un producto es eliminado.                             |
| `product.updated`     | producto  | Ocurre cuando un producto es actualizado.                           |

---

<a name="consultar-todos-los-eventos"></a>
## Consultar todos los eventos

```
GET /v1/events
```

```json
{
  "data": [
    {
      "id": "evn_cixl4l0bf00008704neex2su8",
      "object": "event",
      "kind": "collection.deleted",
      "data": {
        "object": {
          "id": "col_cixjoxfit00008604avrtjfux",
          "object": "collection",
          "permalink": "mochilas",
          "title": "Mochilas",
          "description": "",
          "meta_title": "Mochilas",
          "meta_description": "",
          "kind": "smart",
          "sorting_rule": "manual",
          "image_url": "\/storage\/store1\/images\/IMG_5342.JPG?v=1481523968",
          "is_visible": true,
          "visible_at": 1483579260,
          "created_at": 1483579498,
          "updated_at": 1483579498,
          "rules": [
            {
              "id": "rul_cixjsbg3700008604yogis5k9",
              "object": "collection_rule",
              "field": "product-title",
              "condition": "contains",
              "value": "Backpack"
            }
          ]
        }
      },
      "pending_webhooks": 0,
      "created_at": 1483666259,
      "updated_at": 1483666266
    },
    {
      "id": "evn_ciwmpd8sa00039u04wle6ozew",
      "object": "event",
      "kind": "collection.created",
      "data": {
        "object": {
          ...
        }
      },
      "pending_webhooks": 0,
      "created_at": 1483666259,
      "updated_at": 1483666266
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

<a name="consultar-un-evento"></a>
## Consultar un Evento

```
GET /v1/events/{id}
```

```json
{
  "data": {
    "id": "evn_cixl4l0bf00008704neex2su8",
    "object": "event",
    "kind": "collection.deleted",
    "data": {
      "object": {
        "id": "col_cixjoxfit00008604avrtjfux",
        "object": "collection",
        "permalink": "mochilas",
        "title": "Mochilas",
        "description": "",
        "meta_title": "Mochilas",
        "meta_description": "",
        "kind": "smart",
        "sorting_rule": "manual",
        "image_url": "\/storage\/store1\/images\/IMG_5342.JPG?v=1481523968",
        "is_visible": true,
        "visible_at": 1483579260,
        "created_at": 1483579498,
        "updated_at": 1483579498,
        "rules": [
          {
            "id": "rul_cixjsbg3700008604yogis5k9",
            "object": "collection_rule",
            "field": "product-title",
            "condition": "contains",
            "value": "Backpack"
          }
        ]
      }
    },
    "pending_webhooks": 0,
    "created_at": 1483666259,
    "updated_at": 1483666266
  }
}
```

#### Parámetros

Ningúno.
