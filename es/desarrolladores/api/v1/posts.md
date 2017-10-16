- [Intro](#intro)
- [Objeto de Artículo](#objeto-de-articulo)
- [Consultar todos los Artículos](#consultar-todos-los-articulos)
- [Consultar un Artículo](#consultar-un-articulo)

***

<a name="intro"></a>
# Artículo API

Artículos representan el listado de artículo en una tienda.

---

<a name="objeto-de-articulo"></a>
## Objeto de Artículo

| Atributo            | Tipo      | Descripión                                                           |
|-------------------- |-----------|----------------------------------------------------------------------|
| `id`                | cadena    | Identificador único del artículo.                                    |
| `object`            | cadena    | El nombre del tipo de objeto.                                        |
| `permalink`         | cadena    | El permalink único del artículo.                                     |
| `title`             | cadena    | El título del artículo.                                              |
| `summary`           | cadena    | Un resúmen del artículo.                                             |
| `content`           | cadena    | El contenido del artículo.                                           |
| `meta_title`        | cadena    | El nombre a usar en SEO.                                             |
| `meta_description`  | cadena    | La descripción a usar en SEO.                                        |
| `image_url`         | cadena    | La imagen principal del artículo.                                    |
| `blog_id`           | cadena    | El indentificador único del blog al que pertenece el artículo.       |
| `user_id`           | cadena    | El indentificador único del autor al que pertenece el artículo.      |
| `is_published`      | booleano  | Si el página ha sido publicada.                                      |
| `published_at`      | timestamp | Fecha de publicación del artículo.                                   |
| `created_at`        | timestamp | Fecha de creación del artículo.                                      |
| `updated_at`        | timestamp | Última fecha de actualización del artículo.                          |

---

<a name="consultar-todos-los-articulos"></a>
## Consultar todos los Artículos

```
GET /v1/posts
```

```json
{
  "data": [
    {
      "id": "pst_ciwloy2bi0006vj04v8svsoyx",
      "object": "post",
      "permalink": "primera-noticia",
      "title": "Primera noticia",
      "summary": "",
      "content": "<p>Este es el blog oficial de tu tienda.<\/p>",
      "meta_title": "Primera noticia",
      "meta_description": "",
      "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
      "blog_id": "blg_ciwloy2a30005vj049m3xw7ls",
      "user_id": "usr_ciwloxto60001vj04brc4dmcb",
      "is_published": true,
      "published_at": 1481523660,
      "created_at": 1481523678,
      "updated_at": 1482189827
    },
    {
      "id": "pst_ciwloy2bi0006vj04v8svsoyx",
      "object": "post",
      "permalink": "segunda-noticia",
      "title": "Segunda noticia",
      "summary": "",
      "content": "<p>Este es el blog oficial de tu tienda.<\/p>",
      "meta_title": "Segunda noticia",
      "meta_description": "",
      "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
      "blog_id": "blg_ciwloy2a30005vj049m3xw7ls",
      "user_id": "usr_ciwloxto60001vj04brc4dmcb",
      "is_published": true,
      "published_at": 1481523660,
      "created_at": 1481523678,
      "updated_at": 1482189827
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

<a name="consultar-un-articulo"></a>
## Consultar un Artículo

```
GET /v1/posts/{id}
```

```json
{
  "data": {
    "id": "pst_ciwloy2bi0006vj04v8svsoyx",
    "object": "post",
    "permalink": "primera-noticia",
    "title": "Primera noticia",
    "summary": "",
    "content": "<p>Este es el blog oficial de tu tienda.<\/p>",
    "meta_title": "Primera noticia",
    "meta_description": "",
    "image_url": "https:\/\/cdn-shoperti.global.ssl.fastly.net\/shoperti\/images\/estampas.png?v=1444914699",
    "blog_id": "blg_ciwloy2a30005vj049m3xw7ls",
    "user_id": "usr_ciwloxto60001vj04brc4dmcb",
    "is_published": true,
    "published_at": 1481523660,
    "created_at": 1481523678,
    "updated_at": 1482189827
  }
}
```

#### Parámetros

Ningúno.
