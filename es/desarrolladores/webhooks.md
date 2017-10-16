- [Intro](#intro)
- [Configuación](#configuracion)
- [Recibiendo](#recibiendo)
- [Recibiendo con CSRF](#recibiendo-csrf)
- [Respondiendo](#respondiendo)
- [Verificando Eventos](#verificando-eventos)
- [Estructura y Eventos](#estrucura-y-eventos)

***

<a name="intro"></a>
# Webhooks

Un **Webhook** es una notificación que se genera cuando un evento sucede en una tienda de Shoperti por medio de HTTP POST. Por ejemplo, cuando un cliente genera una orden nueva, nuestro sistema notifica a tu servidor por medio de una URL previamente definida, enviando un HTTP POST con la información de la orden y de esta manera puedas reaccionar al evento.

---

Al integrar productos de terceros en tu negocio puedes tener algunos retos:

- Sincronizar dos sistemas para llevar control completo.
- Poder ejecutar código específico cuando un evento sucede.
- Saber cuándo ocurre una actualización en tu tienda en lugar de sondear regularmente.

Para esto y más sirven principalmente los Webhooks. En vez de tener que estar revisando cada cierto tiempo si un evento sucedió, como por ejemplo, si un cliente creo una orden en tu tienda, con los Webhooks puedes suscribirte al evento y esperar a que llegue la notificación. Esto hace que utilices menos peticiones al API y puedas crear aplicaciones más robustas.

---

<a name="configuracion"></a>
### Configurando tus Webhooks

Los Webhooks se configuran en la sección de desarolladores, haciendo clic en el botón de **Agregar Webhook**.

Ingresa una URL de destino donde quieres que notifiquemos el evento y elige los eventos a los cuales quieras registrarte. Esta URL debe de ser una sección dedicada en tu servidor para poder recibir y contestar a la notificación.

---

<a name="recibiendo"></a>
### Recibiendo Webhooks

Crear un endpoint para recibir un Webhook, es igual que crear cualquier endpoint para recibir cualquier petición a una página de tu sitio. Con PHP, puede ser creando un archivo **.php** o usando cualquier tipo de framework como Laravel o Sinatra, agregando una ruta con el URL deseado.

Los datos de los Webhooks se envían en formato JSON en el cuerpo de la petición.

#### Ejemplo PHP
```php
// Recibir el cuerpo de la petición.
$input = @file_get_contents("php://input");
// Parsear el contenido como JSON.
$eventJson = json_decode($input);

// Usar los datos del Webhooks para alguna acción.

// Responder
http_response_code(200);
```

#### Ejemplo Ruby
```ruby
require "json"

# Usando Sinatra
post "/my/webhook/url" do
  # Recibir el cuerpo de la petición y parsear a JSON.
  event_json = JSON.parse(request.body.read)

  # Usar los datos del Webhooks para alguna acción.

  status 200
end
```

---

<a name="recibiendo-csrf"></a>
### Recibiendo Webhooks con un servidor protegido con CSRF

Si usas algún framework como Laravel, Rails o Django, tu sitio puede estar protegido automáticamente con CSRF tokens en las rutas tipo POST. Esta es una medida de seguridad bastante importante para proteger tu sitio y a tus usuarios de ataques cross-site request forgery. Sin embargo, esto puede prevenir que el servidor no procese los Webhooks de forma adecuada, por lo que puede ser preferible desactivar el CSRF únicamente de la ruta para recibir Webhooks.

#### Ejemplo con Laravel
```php
<?php

namespace App\Http\Middleware;

use Illuminate\Foundation\Http\Middleware\VerifyCsrfToken as BaseVerifier;

class VerifyCsrfToken extends BaseVerifier
{
    /**
     * The URIs that should be excluded from CSRF verification.
     *
     * @var array
     */
    protected $except = [
        '/shoperti/webhook', // URI de tu aplicación
    ];
}
```

---

<a name="respondiendo"></a>
### Respondiendo a los Webhooks

Para que Shoperti esté enterado que el Webhook fue recibido por la aplicación, es necesario que el responda con un HTTP STATUS CODE `2xx`. En caso de responder con cualquier otro código no incluido en este rango, incluyendo los `3xx`, le indicará a Shoperti que no fue recibido el Webhooks.

Si un Webhook no es recibido por cualquier razón, Shoperti intentará seguir notificando una vez cada hora por 2 días. Una vez pasado este tiempo los Webhooks serán marcados como no exitosos y no se podrán reintentar.


---

<a name="verificando-eventos"></a>
### Verificando eventos

Para poder verificar los eventos que envían los Webhooks, puedes usar nuestro API y usando el ID del evento hacer una petición para estar seguro que el evento pertenece a tu cuenta.

---

<a name="estrucura-y-eventos"></a>
### Estructura y Eventos

Los Webhooks en su estructura o cuerpo, contienen objectos de `Eventos` regidos por el API. Puedes leer más de ellos en nuestra [guía de eventos](/ayuda/desarrolladores/api/v1/eventos).
