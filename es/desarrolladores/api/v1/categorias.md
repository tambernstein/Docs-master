- [Intro](#intro)
- [Objeto de Categoría](#objeto-de-categoria)
- [Consultar todas las Categorías](#consultar-todas-las-categorias)
- [Consultar las Categorías en Árbol](#consultar-las-categorias-en-arbol)
- [Consultar una Categoría](#consultar-una-categoria)
- [Consultar una Categoría en Árbol](#consultar-una-categoria-en-arbol)
- [Crear una Categoría](#crear-una-categoria)
- [Actualizar una Categoría](#actualizar-una-categoria)
- [Eliminar una Categoría](#eliminar-una-categoria)

***

<a name="intro"></a>
# Categorías API

Categorías representan el listado de colección en una tienda.

---

<a name="objeto-de-categoria"></a>
## Objeto de Categoría

| Atributo           | Tipo      | Descripión                                                           |
|--------------------|-----------|----------------------------------------------------------------------|
| `id`               | cadena    | Identificador único de la categoría.                                 |
| `object`           | cadena    | El nombre del tipo de objeto.                                        |
| `permalink`        | cadena    | El permalink único de la categoría.                                  |
| `title`            | cadena    | El nombre de la categoría.                                           |
| `order`            | entero    | Posición en el cual se muestra la categría.                          |
| `parent_id`        | cadena    | Identificador de la categoría padre.                                 |
| `created_at`       | timestamp | Fecha de creación de la categoría.                                   |
| `updated_at`       | timestamp | Última fecha de actualización de la categoría.                       |
| `children[]`       | arreglo   | Las categorías hijo de la categoría.                                 |

---

<a name="consultar-todas-las-categorias"></a>
## Consultar todas las Categorías

```
GET /v1/categories
```

```json
{
  "data": [
    {
      "id": "cat_ciy2aof6o0000wv04kd4nzutn",
      "object": "category",
      "permalink": "lentes",
      "title": "Lentes",
      "order": 0,
      "parent_id": "cat_ciy2ao95s00004y04dnrajijx"
    },
    {
      "id": "cat_ciy2ao95s00004y04dnrajijx",
      "object": "category",
      "permalink": "hombre",
      "title": "Hombre",
      "order": 0,
      "parent_id": null
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

<a name="consultar-las-categorias-en-arbol"></a>
## Consultar las Categorías en forma de Árbol

```
GET /v1/categories/tree
```

```json
{
  "data": [
    {
      "id": "cat_ciy2ao95s00004y04dnrajijx",
      "object": "category",
      "permalink": "hombre",
      "title": "Hombre",
      "order": 0,
      "parent_id": null,
      "updated_at": 1484684422,
      "created_at": 1484684422,
      "children": [
        {
          "id": "cat_ciy2aof6o0000wv04kd4nzutn",
          "object": "category",
          "permalink": "lentes",
          "title": "Lentes",
          "order": 0,
          "parent_id": "cat_ciy2ao95s00004y04dnrajijx",
          "updated_at": 1484684422,
          "created_at": 1484684422,
          "children": []
        }
      ]
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

<a name="consultar-una-categoria"></a>
## Consultar una Categoría

```
GET /v1/categories/{id}
```

```json
{
  "data": {
    "id": "cat_ciy2aof6o0000wv04kd4nzutn",
    "object": "category",
    "permalink": "lentes",
    "title": "Lentes",
    "order": 0,
    "parent_id": "cat_ciy2ao95s00004y04dnrajijx",
    "updated_at": 1484684422,
    "created_at": 1484684422
  }
}
```

#### Parámetros

Ningúno.

---

<a name="consultar-una-categoria-en-arbol"></a>
## Consultar una Categoría en forma de Árbol

```
GET /v1/categories/{id}/tree
```

```json
{
  "data": {
    "id": "cat_ciy2ao95s00004y04dnrajijx",
    "object": "category",
    "permalink": "hombre",
    "title": "Hombre",
    "order": 0,
    "parent_id": null,
    "updated_at": 1484684422,
    "created_at": 1484684422,
    "children": [
      {
        "id": "cat_ciy2aof6o0000wv04kd4nzutn",
        "object": "category",
        "permalink": "lentes",
        "title": "Lentes",
        "order": 0,
        "parent_id": "cat_ciy2ao95s00004y04dnrajijx",
        "updated_at": 1484684422,
        "created_at": 1484684422,
        "children": []
      }
    ]
  }
}
```

#### Parámetros

Ningúno.

---

<a name="crear-una-categoria"></a>
## Crear una Categoría

```
POST /v1/categories
```

#### Parámetros

| Nombre              | Tipo      | Requerido | Descripión                                                     |
|-------------------- |-----------|-----------|----------------------------------------------------------------|
| `title`             | cadena    | true      | El nombre de la categoría.                                     |
| `parent_id`         | cadena    | false     | Identificador de la categoría padre.                           |
| `order`             | entero    | false     | Posición en el cual se muestra la categría.                    |

Si es exitoso la respuesta será un objeto de `categoría`.

---

<a name="actualizar-una-categoria"></a>
## Actualizar una Categoría

```
POST /v1/categories/{id}
```

#### Parámetros

| Nombre              | Tipo      | Requerido | Descripión                                                     |
|-------------------- |-----------|-----------|----------------------------------------------------------------|
| `title`             | cadena    | true      | El nombre de la categoría.                                     |
| `parent_id`         | cadena    | false     | Identificador de la categoría padre.                           |
| `order`             | entero    | false     | Posición en el cual se muestra la categría.                    |

Si es exitoso la respuesta será un objeto de `categoría`.

---

<a name="eliminar-una-categoria"></a>
## Eliminar una Categoría

```
DELETE /v1/categories/{id}
```

#### Parámetros

Ningúno.

Si es exitoso la respuesta será un HTTP `204 No Content`.

