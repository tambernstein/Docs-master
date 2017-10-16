- [Intro](#intro)
- [Objeto de Dirección](#objeto-de-direccion)
- [Consultar todos las Direcciones](#consultar-todas-las-direcciones)
- [Consultar un Dirección](#consultar-una-direccion)

***

<a name="intro"></a>
# Direcciones Clientes API

Direcciones Clientes representan el listado de direcciones de los clientes en una tienda.

---

<a name="objeto-de-direccion"></a>
## Objeto de Dirección

| Atributo            | Tipo      | Descripión                                                           |
|-------------------- |-----------|----------------------------------------------------------------------|
| `id`                | cadena    | Identificador único de la dirección.                                 |
| `object`            | cadena    | El nombre del tipo de objeto.                                        |
| `first_name`        | cadena    | El nombre del cliente.                                               |
| `last_name`         | cadena    | El o los apellidos del cliente.                                      |
| `address1`          | cadena    | La calle de la dirección.                                            |
| `address2`          | cadena    | Información adicional sobre la dirección.                            |
| `country`           | cadena    | El país de la dirección.                                             |
| `country_code`      | cadena    | El código en ISO 3166-1 (alpha-2) del país de la dirección.          |
| `state`             | cadena    | El estado de la dirección.                                           |
| `state_code`        | cadena    | El código del estado de la dirección.                                |
| `city`              | cadena    | La ciudad de la dirección.                                           |
| `postcode`          | cadena    | El código postal de la dirección.                                    |
| `phone`             | cadena    | El teléfono de la dirección.                                         |
| `company`           | cadena    | El nombre de la compañia de la dirección.                            |
| `references`        | cadena    | Las referencias de la dirección.                                     |
| `is_primary`        | booleano  | Indicador si la dirección es la primaria.                            |
| `created_at`        | timestamp | Fecha de creación de la dirección.                                   |
| `updated_at`        | timestamp | Última fecha de actualización de la dirección.                       |

---

<a name="consultar-todas-las-direcciones"></a>
## Consultar todas las Direcciones de un Cliente

```
GET /v1/customers/{id}/addresses
```

```json
{
  "data": [
    {
      "id": "adr_ciwmplu6s00019u04hir3x4ry",
      "object": "customer_address",
      "first_name": "Joe",
      "last_name": "Doe",
      "address1": "Calle Hamburgo #218",
      "address2": "Roma Norte",
      "country": "Mexico",
      "country_code": "MX",
      "state": "Ciudad de M\u00e9xico",
      "state_code": "DF",
      "city": "Mexico",
      "postcode": "06600",
      "phone": "5521231637",
      "company": null,
      "references": "",
      "is_primary": true,
      "created_at": 1481585253,
      "updated_at": 1481585253
    },
    {
      "id": "adr_ciwwl775c00005c04g2iscwxt",
      "object": "customer_address",
      "first_name": "Maria",
      "last_name": "Lopez",
      "address1": "Colima #233",
      "address2": "Roma Norte",
      "country": "Mexico",
      "country_code": "MX",
      "state": "Ciudad de M\u00e9xico",
      "state_code": "DF",
      "city": "Mexico",
      "postcode": "06700",
      "phone": "5521231637",
      "company": null,
      "references": "",
      "is_primary": true,
      "created_at": 1481585253,
      "updated_at": 1481585253
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

<a name="consultar-una-direccion"></a>
## Consultar una Dirección de un Cliente

```
GET /v1/customers/{id}/addresses/{id}
```

```json
{
  "data": {
    "id": "adr_ciwwl775c00005c04g2iscwxt",
    "object": "customer_address",
    "first_name": "Maria",
    "last_name": "Lopez",
    "address1": "Colima #233",
    "address2": "Roma Norte",
    "country": "Mexico",
    "country_code": "MX",
    "state": "Ciudad de M\u00e9xico",
    "state_code": "DF",
    "city": "Mexico",
    "postcode": "06700",
    "phone": "5521231637",
    "company": null,
    "references": "",
    "is_primary": true,
    "created_at": 1481585253,
    "updated_at": 1481585253
  }
}
```

#### Parámetros

Ningúno.
