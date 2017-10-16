- [Intro](#intro)

***

<a name="intro"></a>
# Openpay

Openpay es una plataforma de pagos que permite de manera rápida y sencilla aceptar distintos métodos de pago en tu sitio web o app. 

Openpay te ofrece diferentes medios de pago para tus clientes, ellos podrán pagar por medio de: 

*   Tarjetas de crédito
*   Tarjetas de débito
*   Pagos en tiendas de conveniencia desde múltiples puntos a lo largo del país. 
*   Transferencias interbancarias SPEI (Sistema de Pagos Electrónicos Interbancarios). Puedes consultar más información [aquí](http://www.banxico.org.mx/sistemas-de-pago/servicios/sistema-de-pagos-electronicos-interbancarios-spei/sistema-pagos-electronicos-in.html)

Para conocer más acerca de los distintos medios de pago que podrás ofrecer por medio de Openpay, ingresa [aquí](http://www.openpay.mx/como-funciona.html).

Integrar **Openpay** como método de pago es bastante sencillo, si sigues este tutorial paso a paso tendrás lista la integración en unos pocos minutos.

---

#### Para abrir una cuenta en Openpay

Ingresa a [https://openpay.mx/login/register](https://sandbox-dashboard.openpay.mx/login/register)

*   Completa todos los datos que se solicitan, recuerda incluir la palabra **Shoperti** en el campo que dice **empresa o persona que te referenció**.
*   Cuando termines de completar tus datos, acepta los Términos de Servicio de Openpay.
*   Haz clic sobre el botón **Registrarme**.

[![Openpay](/img/help/settings/single/openpay.jpg){.img-responsive}](/img/help/settings/single/openpay.jpg)

Recibirás un las instrucciones a seguir para activar tu cuenta en la dirección de correo electrónico que hayas proporcionado. 

#### Para activar tu cuenta

Da clic en la parte superior izquierda en el botón que dice **acceso a producción**. 

[![Openpay](/img/help/settings/single/openpay-activate1.jpg){.img-responsive}](/img/help/settings/single/openpay-activate1.jpg)

Deberás de dar de alta tu información comercial y fiscal, datos del representante, datos de factura electrónica, la información de tu cuenta bancaria y los datos del administrador de cuenta.

[![Openpay](/img/help/settings/single/openpay-activate2.jpg){.img-responsive}](/img/help/settings/single/openpay-activate2.jpg)

La documentación será validada por el área administrativa, lo cual tomará un **tiempo máximo de 24 hrs hábiles**. Se realizará una validación técnica de tu sitio y en un máximo de **48 a 72 hrs hábiles**, recibirás noticias con el resultado de la validación técnica. 

#### API Keys

Las llaves para modo **Sandbox**, sirven para procesar cargos a manera de prueba, al utilizar estas llaves no se genera ningún cargo real a la tarjeta o a cualquier método de pago, estas son utilizadas para probar la implementación antes de salir con tu tienda en vivo. Así que es importante que sean las **llaves de prueba** las que configures en Shoperti ANTES de que validen tu cuenta y tengas acceso a las **llaves de producción**.

[![Openpay](/img/help/settings/single/openpay-keys.jpg){.img-responsive}](/img/help/settings/single/openpay-keys.jpg)

Para que **Openpay** pueda validar tu cuenta, primero deberás de reigstrar las llaves de prueba en tu administrador. 

Una vez que tu cuenta quede validada, dentro del panel de **producción**, podrás extraer:

* ID
* Llave Privada de producción
* Llave Pública de producción

Ten cuidado al ingresar tus llaves de configuración, ya que si usas las **llaves de prueba** en lugar de las de **producción** -una vez que quede validad tu cuenta-, **NO** se realizarán cargos reales a tus clientes. Así que estas son las llaves que deberás de utilizar cuando hagas pública tu tienda y comiences a vender. Recuerda que todo lo relacionado a tus ventas y depósitos a tu cuenta lo podrás verificar directamente en el panel de Openpay, así como en tu panel de órdenes en Shoperti.

#### Integrando Openpay en Shoperti 

Para integrar Openpay como método de pago en Shoperti lo único que tienes que hacer es copiar el **ID** y las **llaves de producción pública y privada** y llenar los datos en la configuración del método de pago. 

[![Openpay](/img/help/settings/single/openpay-configure.jpg){.img-responsive}](/img/help/settings/single/openpay-configure.jpg)

#### Página de términos y condiciones:

Para generar tu página de términos y condiciones, puedes ingresar a [https://www.shoperti.com/herramientas/generadores/terminos-y-condiciones](/herramientas/generadores/terminos-y-condiciones) y aprovechar que hemos hecho una herramienta que te permite generar un machote para tu tienda. Solo tienes que llenar ciertos datos, puedes encontrar el generador aquí: [https://www.shoperti.com/herramientas](/herramientas).

Ahora necesitas agregar tu página de términos y condiciones que creaste directamente en tu tienda Shoperti, para esto ingresa a tu cuenta, haz clic en la sección de **contenidos** y crea una página titulada **términos y condiciones**. Para mostrar el acceso a esta página, puedes configurarlo haciendo clic en "**tienda en línea**" en tu administrador de shoperti, accediendo a **menús** y configurando tu **página** de términos y condiciones por ejemplo como parte del menú del **footer** de tu tienda.

#### Meses sin intereses con Openpay

Poder recibir pagos a **meses sin intereses** es una forma de pago que te permite ofrecer una promoción a tu cliente para cobrar en **pagos divididos en mensualidades sin generar intereses**. A ti te permite recibir el monto total de venta en la cuenta bancaria que hayas indicado al momento de registrarte, menos comisión de meses sin intereses en una sola exhibición, además podrás incrementar ventas de un ticket alto gracias a la comodidad de pagarlas a un plazo y el banco se encargará de cobrar al tarjetahabiente en el lapso establecido.

Estas promociones consisten en que el cliente adquiera productos o servicios con una tarjeta de crédito mexicana hasta en **3, 6, 9 o 12 pagos fijos y sin intereses**.

Cuando un cliente concreta una compra a Meses Sin Intereses, el banco toma el monto total de la compra de la línea de crédito del cliente y lo divide por el número de meses de la promoción. A partir de ese momento, empezará a generar cargos mensuales por la cantidad correspondiente sin cobrar ningún tipo de interés al tarjeta habiente.

Conforme el cliente vaya pagando la mensualidad correspondiente, el banco informará en el estado de cuenta del cliente el detalle de la compra así como la mensualidad que está pagando.

[![Openpay](/img/help/settings/single/openpay-msi.jpg){.img-responsive}](/img/help/settings/single/openpay-msi.jpg)

Para conocer más sobre la **guía de meses sin intereses de Openpay** ingresa a: [http://www.openpay.mx/costos.html](http://www.openpay.mx/costos.html)

Para poder ofrecer meses sin intereses con **Openpay** en tu tienda de **Shoperti**, lo único que tienes que hacer es **activar el plazo de meses sin intereses** que deseas ofrecer.

Finalmente haz clic en **activar método** y ¡listo! ya puedes ofrecer **meses sin intereses** con **Openpay** en tu tienda de **Shoperti**.
