- [Intro](#intro)
- [Objeto de Cliente](#objeto-de-cliente)
- [Consultar todos los Clientes](#consultar-todos-los-clientes)
- [Consultar un Cliente](#consultar-un-cliente)
- [Crear un Cliente](#crear-un-cliente)
- [Actualizar un Cliente](#actualizar-un-cliente)
- [Autenticar un Cliente](#autenticar-un-cliente)

***

<a name="intro"></a>
# Clientes API

Clientes representan el listado de clientes en una tienda.

---

<a name="objeto-de-cliente"></a>
## Objeto de Cliente

| Atributo            | Tipo      | Descripión                                                           |
|-------------------- |-----------|----------------------------------------------------------------------|
| `id`                | cadena    | Identificador único del cliente.                                     |
| `object`            | cadena    | El nombre del tipo de objeto.                                        |
| `name`              | cadena    | El nombre del cliente.                                               |
| `first_name`        | cadena    | El nombre del cliente.                                               |
| `last_name`         | cadena    | El o los apellidos del cliente.                                      |
| `email`             | cadena    | El correo electrónico del cliente.                                   |
| `is_newsletterable` | booleano  | Si el cliente puede ser contactado para promociones.                 |
| `is_active`         | booleano  | Si el cliente está activo para venta.                                |
| `notes`             | cadena    | Notas agregadas por la tienda al cliente.                            |
| `created_at`        | timestamp | Fecha de creación del cliente.                                       |
| `updated_at`        | timestamp | Última fecha de actualización del cliente.                           |
| `tags[]`            | arreglo   | Las etiquetas asignadas a un cliente.                                |
| `default_address`   | objeto    | La dirección primaria del cliente                                    |
| `addresses[]`       | arreglo   | Las direcciones almacenadas del cliente                              |

---

<a name="consultar-todos-los-clientes"></a>
## Consultar todos los Clientes

```
GET /v1/customers
```

```json
{
  "data": [
    {
      "id": "cus_citpanw0r00002orr2txogcpb",
      "object": "customer",
      "name": "Joe Doe",
      "first_name": "Joe",
      "last_name": "Doe",
      "email": "joe@example.com",
      "is_newsletterable": true,
      "is_active": true,
      "notes": "¡Excelente cliente!",
      "tags": [],
      "default_address": {
        "id": "adr_citpanw1000012orrzjvhpsny",
        "object": "customer_address",
        "first_name": "Juan",
        "last_name": "Tremendo",
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
        "created_at": 1475211206,
        "updated_at": 1477583336,
      },
      "addresses": [
        {
          "id": "adr_citpanw1000012orrzjvhpsny",
          "object": "customer_address",
          "first_name": "Joe",
          "last_name": "Doe",
          "address1": "Calle Hamburgo #218",
          "address2": "Roma Norte",
          "references": "",
          "company": "",
          "postcode": "06600",
          "city": "Mexico",
          "state": "Ciudad de Mexico",
          "state_code": "DF",
          "country": "Mexico",
          "country_code": "MX",
          "phone": "552445807",
          "is_primary": true,
          "created_at": 1475211206,
          "updated_at": 1477583336,
        }
      ],
      "created_at": 1475211206,
      "updated_at": 1478756285
    },
    {
      "id": "cus_ciusjnk720000egrrj0k8ojfb",
      "object": "customer",
      "name": "Lori Ruiz",
      "first_name": "Lori",
      "last_name": "Ruiz",
      "email": "lori@example.com",
      "is_newsletterable": false,
      "is_active": true,
      "notes": "",
      "tags": [],
      "default_address": null,
      "addresses": [],
      "created_at": 1477584488,
      "updated_at": 1481309565
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

<a name="consultar-un-cliente"></a>
## Consultar un Cliente

```
GET /v1/customers/{id}
```

```json
{
  "data": {
    "id": "cus_citpanw0r00002orr2txogcpb",
    "object": "customer",
    "name": "Joe Doe",
    "first_name": "Joe",
    "last_name": "Doe",
    "email": "joe@example.com",
    "is_newsletterable": true,
    "is_active": true,
    "notes": "¡Excelente cliente!",
    "tags": [],
    "default_address": {
      "id": "adr_citpanw1000012orrzjvhpsny",
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
      "created_at": 1475211206,
      "updated_at": 1477583336,
    },
    "addresses": [
      {
        "id": "adr_citpanw1000012orrzjvhpsny",
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
        "created_at": 1475211206,
        "updated_at": 1477583336,
      }
    ],
    "created_at": 1475211206,
    "updated_at": 1478756285
  }
}
```

#### Parámetros

Ningúno.

---

<a name="crear-un-cliente"></a>
## Crear un Cliente

```
POST /v1/customers
```

#### Parámetros

| Nombre              | Tipo      | Requerido | Descripión                                               |
|-------------------- |-----------|-----------|----------------------------------------------------------|
| `first_name`        | cadena    | false     | El nombre del cliente.                                   |
| `last_name`         | cadena    | false     | El o los apellidos del cliente.                          |
| `email`             | cadena    | true      | El correo electrónico del cliente.                       |
| `is_newsletterable` | booleano  | false     | Si el cliente puede ser contactado para promociones.     |
| `is_active`         | booleano  | false     | Si el cliente está activo para venta.                    |
| `notes`             | cadena    | false     | Notas agregadas por la tienda al cliente.                |
| `tags[]`            | arreglo   | false     | Las etiquetas asignadas a un cliente.                    |

Si es exitoso la respuesta será un objeto de `cliente`.

---

<a name="actualizar-un-cliente"></a>
## Actualizar un Cliente

```
POST /v1/customers/{id}
```

#### Parámetros

| Nombre              | Tipo      | Requerido | Descripión                                               |
|-------------------- |-----------|-----------|----------------------------------------------------------|
| `first_name`        | cadena    | false     | El nombre del cliente.                                   |
| `last_name`         | cadena    | false     | El o los apellidos del cliente.                          |
| `email`             | cadena    | true      | El correo electrónico del cliente.                       |
| `is_newsletterable` | booleano  | false     | Si el cliente puede ser contactado para promociones.     |
| `is_active`         | booleano  | false     | Si el cliente está activo para venta.                    |
| `notes`             | cadena    | false     | Notas agregadas por la tienda al cliente.                |
| `tags[]`            | arreglo   | false     | Las etiquetas asignadas a un cliente.                    |

Si es exitoso la respuesta será un objeto de `cliente`.

---

<a name="autenticar-un-cliente"></a>
## Autenticar un Cliente

```
POST /v1/customers/token
```

#### Parámetros

| Nombre     | Tipo   | Requerido | Descripción                          |
|------------|--------|-----------|--------------------------------------|
| `email`    | cadena | true      | Correo electrónico del cliente.      |
| `password` | cadena | true      | Contraseña del cliente.              |

Si es exitoso la respuesta será un objeto de `cliente` más un token.

```json
{
  "data": {
    "id": "cus_citpanw0r00002orr2txogcpb",
    "object": "customer",
    "name": "Joe Doe",
    "first_name": "Joe",
    "last_name": "Doe",
    "email": "joe@example.com",
    "is_newsletterable": true,
    "is_active": true,
    "notes": "¡Excelente cliente!",
    "tags": [],
    "default_address": null,
    "addresses": [],
    "created_at": 1475211206,
    "updated_at": 1478756285,
    "token": "ak_ciy546xzt00004y04ltqkd7l2T6j1GpeSd87g3s"
  }
}
```
