- [Intro](#intro)
- [Objeto de Blog](#objeto-de-blog)
- [Consultar todos los Blogs](#consultar-todos-los-blogs)
- [Consultar un Blog](#consultar-un-blog)

***

<a name="intro"></a>
# Blogs API

Blogs representan el listado de blogs en una tienda.

---

<a name="objeto-de-blog"></a>
## Objeto de Blog

| Atributo           | Tipo      | Descripión                                                           |
|--------------------|-----------|----------------------------------------------------------------------|
| `id`               | cadena    | Identificador único del blog.                                        |
| `object`           | cadena    | El nombre del tipo de objeto.                                        |
| `permalink`        | cadena    | El permalink único del blog.                                         |
| `title`            | cadena    | El título del blog.                                                  |
| `meta_title`       | cadena    | El nombre a usar en SEO.                                             |
| `meta_description` | cadena    | La descripción a usar en SEO.                                        |
| `is_commentable`   | booleano  | Si el blog está habilitado para comentarios de los cientes.          |
| `created_at`       | timestamp | Fecha de creación del blog.                                          |
| `updated_at`       | timestamp | Última fecha de actualización del blog.                              |

---

<a name="consultar-todos-los-blogs"></a>
## Consultar todos los Blogs

```
GET /v1/blogs
```

```json
{
  "data": [
    {
      "id": "blg_ciwwp37wo00008i04rvpqdkbt",
      "object": "blog",
      "permalink": "novedades",
      "title": "Novedades",
      "meta_title": "Novedades",
      "meta_description": "Nuestros productos de novedad.",
      "is_commentable": false,
      "created_at": 1482189046,
      "updated_at": 1482189046
    },
    {
      "id": "blg_ciwloy2a30005vj049m3xw7ls",
      "object": "blog",
      "permalink": "noticias",
      "title": "Noticias",
      "meta_title": "Noticias",
      "meta_description": null,
      "is_commentable": false,
      "created_at": 1481523678,
      "updated_at": 1481523678
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

<a name="consultar-un-blog"></a>
## Consultar un Blog

```
GET /v1/blogs/{id}
```

```json
{
  "data": {
    "id": "blg_ciwloy2a30005vj049m3xw7ls",
    "object": "blog",
    "permalink": "noticias",
    "title": "Noticias",
    "meta_title": "Noticias",
    "meta_description": null,
    "is_commentable": false,
    "created_at": 1481523678,
    "updated_at": 1481523678
  }
}
```

#### Parámetros

Ningúno.
