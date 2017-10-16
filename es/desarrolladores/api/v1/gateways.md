- [Intro](#intro)
- [Objeto de Gateway](#objeto-de-gateway)
- [Consultar todos los Gateways](#consultar-todos-los-gateways)
- [Consultar un Gateway](#consultar-un-gateway)

***

<a name="intro"></a>
# Gateways API

Gateways representan el listado de gateways en una tienda.

---

<a name="objeto-de-gateway"></a>
## Objeto de Gateway

| Atributo           | Tipo      | Descripión                                                           |
|--------------------|-----------|----------------------------------------------------------------------|
| `id`               | cadena    | Identificador único del gateway.                                     |
| `object`           | cadena    | El nombre del tipo de objeto.                                        |
| `name`             | cadena    | El nombre del gateway.                                               |
| `display_name`     | cadena    | El nombre a mostrar del gateway.                                     |
| `source`           | cadena    | El source único del gateway.                                         |
| `driver`           | cadena    | El tipo de conexión que usa el gateway.                              |
| `is_enabled`       | booleano  | Si el gateway está habilitado para el ciente.                        |
| `settings`         | arreglo   | Configuración específica del gateway.                                |
| `created_at`       | timestamp | Fecha de creación del gateway.                                       |
| `updated_at`       | timestamp | Última fecha de actualización del gateway.                           |

---

<a name="consultar-todos-los-gateways"></a>
## Consultar todos los Gateways

```
GET /v1/gateways
```

```json
{
  "data": [
    {
      "id": "gtw_ciws8g1xl00008i04d8d8jiql",
      "object": "gateway",
      "name": "Manual",
      "display_name": "Pago a contra entrega",
      "source": "manual",
      "driver": "manual",
      "is_enabled": true,
      "settings": {
        "instructions": "Por favor da el monto exacto al repartidor."
      },
      "created_at": 1481919227,
      "updated_at": 1481919227
    },
    {
      "id": "gtw_ciwmf5qqg0000vk04w8sod74v",
      "object": "gateway",
      "name": "Conekta",
      "display_name": null,
      "source": "conekta",
      "driver": "conekta",
      "is_enabled": true,
      "settings": {
        "public_key": "key_"
      },
      "created_at": 1481567706,
      "updated_at": 1481567708
    }
  ]
}
```

#### Parámetros

Ningúno.

---

<a name="consultar-un-gateway"></a>
## Consultar un Gateway

```
GET /v1/gateways/{id}
```

```json
{
  "data": {
    "id": "gtw_ciws8g1xl00008i04d8d8jiql",
    "object": "gateway",
    "name": "Manual",
    "display_name": "Pago a contra entrega",
    "source": "manual",
    "driver": "manual",
    "is_enabled": true,
    "settings": {
      "instructions": "Por favor da el monto exacto al repartidor."
    },
    "created_at": 1481919227,
    "updated_at": 1481919227
  }
}
```

#### Parámetros

Ningúno.
