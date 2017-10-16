- [Intro](#intro)
- [Objeto de Página](#objeto-de-pagina)
- [Consultar todas las Páginas](#consultar-todas-las-paginas)
- [Consultar una Página](#consultar-una-pagina)

***

<a name="intro"></a>
# Páginas API

Páginas representan el listado de páginas en una tienda.

---

<a name="objeto-de-pagina"></a>
## Objeto de Página

| Atributo            | Tipo      | Descripión                                                           |
|-------------------- |-----------|----------------------------------------------------------------------|
| `id`                | cadena    | Identificador único de la página.                                    |
| `object`            | cadena    | El nombre del tipo de objeto.                                        |
| `permalink`         | cadena    | El permalink único de la página.                                     |
| `title`             | cadena    | El título de la página.                                              |
| `content`           | cadena    | El contenido de la página.                                           |
| `meta_title`        | cadena    | El nombre a usar en SEO.                                             |
| `meta_description`  | cadena    | La descripción a usar en SEO.                                        |
| `is_published`      | booleano  | Si el página ha sido publicada.                                      |
| `published_at`      | timestamp | Fecha de publicación de la página.                                   |
| `created_at`        | timestamp | Fecha de creación de la página.                                      |
| `updated_at`        | timestamp | Última fecha de actualización de la página.                          |

---

<a name="consultar-todas-las-páginas"></a>
## Consultar todas las Páginas

```
GET /v1/pages
```

```json
{
  "data": [
    {
      "id": "pag_ciwloy2ej0009vj04h47x2okv",
      "object": "page",
      "permalink": "sobre-nosotros",
      "title": "Sobre nosotros",
      "content": "<p>Somos una empresa de venta en línea</p>",
      "meta_title": "Sobre Nosotros",
      "meta_description": null,
      "is_published": true,
      "published_at": 1481523678,
      "created_at": 1481523678,
      "updated_at": 1481523678
    },
    {
      "id": "pag_ciwloy2dz0008vj046pofkh8s",
      "object": "page",
      "permalink": "inicio",
      "title": "P\u00e1gina de Inicio",
      "content": "<p>Bienvenido a nuestra plataforma.<\/p>",
      "meta_title": "P\u00e1gina de inicio",
      "meta_description": null,
      "is_published": true,
      "published_at": 1481523678,
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

<a name="consultar-una-pagina"></a>
## Consultar una Página

```
GET /v1/pages/{id}
```

```json
{
  "data": {
    "id": "pag_ciwloy2ej0009vj04h47x2okv",
    "object": "page",
    "permalink": "sobre-nosotros",
    "title": "Sobre nosotros",
    "content": "<p>Somos una empresa de venta en línea</p>",
    "meta_title": "Sobre Nosotros",
    "meta_description": null,
    "is_published": true,
    "published_at": 1481523678,
    "created_at": 1481523678,
    "updated_at": 1481523678
  }
}
```

#### Parámetros

Ningúno.
