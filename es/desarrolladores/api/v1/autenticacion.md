- [Intro](#intro)
- [OAuth2](#oauth2)
- [HTTP Basic](#http-basic)

***

<a name="intro"></a>
# Autenticación

Nuesto systema de autenticación permite al API de Shoperti verificar que seas un usuario autorizado para poder consultar y modificar datos de una tienda. Contamos con dos métodos, OAuth2 para aplicaciones de terceros y HTTP Basic para aplicaciones privadas.

---

<a name="oauth2"></a>
## OAuth2

Beta, actualmente sólo proveemos acceso beta a crear credenciales, puedes registrarte al programa enviando un correo a [beta@shoperti.com](mailto:beta@shoperti.com) contándonos qué es lo que pretendes construir.

---

<a name="http-basic"></a>
## HTTP Basic

Puedes autenticar a una tienda usando las credenciales de desarrollador que se encuentran en la sección de `Desarrolladores` del adminstrador. Existen dos tipos de autenticación usando estás credenciales, la llave pública y la llave secreta.

#### Llave Pública
La llave pública sirve principalmente para código de cliente y/o aplicaciones móviles. Esto quiere decir que tu llave puede ser visible por terceros, sin embargo mantiene tu información más segura y da la hablidad de poder interactuar con el API de forma límitada.

Lectura
- artículos
- blogs
- carritos
- categorías
- checkouts
- colecciones
- páginas
- próductos
- tokens de clientes

Escritura
- carritos
- checkouts
- tokens de clientes

#### Llave Privada
La llave privada sirve principalmente para código de backend dónde se puede mantener en secreto. Está llave ofrece acceso completo al API y debes de mantenerla fuera de repositorios.

Lectura y Escritura
- artículos
- blogs
- carritos
- categorías
- checkouts
- clientes
- colecciones
- estados
- gateways
- órdenes
- páginas
- próductos
- países
- tokens de clientes

La autenticación al API se hace por medio de [HTTP Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication) usando HTTPS. Usa tu API key como el valor del nombre de usuario. No es necesario ingresar una contraseña.

Ejemplo:
```bash
curl https://app.shoperti.com/api/v1/products \
   -u sk_nwKf5LPpSgJ7ffjZdRrCP2DGsvYyo:
```

```bash
curl https://{tienda}.shoperti.com/api/v1/products \
   -u sk_nwKf5LPpSgJ7ffjZdRrCP2DGsvYyo:
```

Si necesitas autenticación via bearer (ej. para peticiones cross-origin) puedes usar:
```
-H "Authorization: Bearer sk_nwKf5LPpSgJ7ffjZdRrCP2DGsvYyo"
```
en vez de 
```
-u sk_nwKf5LPpSgJ7ffjZdRrCP2DGsvYyo:
```
