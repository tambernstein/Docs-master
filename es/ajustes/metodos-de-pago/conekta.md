- [Intro](#intro)

***

<a name="intro"></a>
# Conekta

Conekta es el principal y más cómodo procesador de pagos que puedes ofrecer a tus clientes, con el uso de este sistema ellos podrán pagar en la modalidad que más les convenga.

*   Tarjetas de crédito
*   Tarjetas de débito
*   Pagos en OXXO
*   Pagos en Ventanillas Bancarias Banorte
*   Transferencias interbancarias SPEI (Sistema de Pagos Electrónicos Interbancarios). Puedes consultar más información [aquí](http://www.banxico.org.mx/sistemas-de-pago/servicios/sistema-de-pagos-electronicos-interbancarios-spei/sistema-pagos-electronicos-in.html)

---

#### Para abrir una cuenta en Conekta

Entra a [https://admin.conekta.io/users/sign_up](https://admin.conekta.io/users/sign_up)

*   En el campo que dice **nombre de la empresa o proyecto**, deberás indicar el **nombre de tu tienda en línea**.
*   Completa todos los datos que se solicitan, recuerda incluir la palabra **Shoperti** en el campo que dice **empresa o persona que te referenció**.
*   Cuando termines de completar tus datos, acepta los Términos de Servicio de Conekta.
*   Haz clic sobre el botón **Registrarme**.

[![Conketa](/img/help/settings/single/conekta.jpg){.img-responsive}](/img/help/settings/single/conekta.jpg)

Una vez realizados los pasos anteriores, ingresarás a la cuenta de Conekta y deberás proceder a activarla.

[![Conketa](/img/help/settings/single/conekta-activate.jpg){.img-responsive}](/img/help/settings/single/conekta-activate.jpg)

#### Activar cuenta

Da clic en la parte superior derecha en el botón que dice **activa tu cuenta** e ingresa toda la información solicitada. Es necesario tengas a la mano:

*   Términos y condiciones de tu tienda en línea
*   En caso de ser persona moral, tu Cédula de Identificación Fiscal y Acta Constitutiva. Si eres persona física con actividad empresarial, solamente tu Cédula de Identificación Fiscal.
*   En caso de ser persona moral, se requiere la identificación del representante legal por ambos lados. Si eres persona física, tu identificación por ambos lados.
*   CLABE para transferencias electrónicas.
*   Copia de la carátula del estado de cuenta bancario. Esto es con la intención de que puedan corroborar los datos a los cuáles se te depositará el dinero de las ventas.

Ahora solamente deberás de esperar de 24 a 48 hrs. para que tu cuenta de Conekta sea activada. En cuánto recibas la notificación de que tu cuenta de Conekta fue activada, es necesario que ingreses y des clic en el menú izquierdo donde dice "**API Keys**" y copies la información que viene debajo de "**Llaves de Producción**" y la pegues dentro de tu administrador de Shoperti en la **sección de ajustes, métodos de pago, conekta**.

#### API Keys

Llaves para modo Sandbox, sirven para procesar cargos a manera de prueba, al utilizar estas llaves no se genera ningún cargo real a la tarjeta o a cualquier método de pago, estas son utilizadas para probar la implementación antes de salir con tu tienda en vivo. Se aplica el mismo proceso para agregar métodos de pago en Oxxo, SPEI, Tarjeta de crédito o débito por medio de Conekta.

#### Página de términos y condiciones:

Para generar tu página de términos y condiciones, puedes ingresar a [https://www.shoperti.com/herramientas/generadores/terminos-y-condiciones](/herramientas/generadores/terminos-y-condiciones) y aprovechar que hemos hecho una herramienta que te permite generar un machote para tu tienda. Solo tienes que llenar ciertos datos, puedes encontrar el generador aquí: [https://www.shoperti.com/herramientas](/herramientas).

Ahora necesitas agregar tu página de términos y condiciones que creaste directamente en tu tienda Shoperti, para esto ingresa a tu cuenta, haz clic en la sección de **contenidos** y crea una página titulada **términos y condiciones**. Para mostrar el acceso a esta página, puedes configurarlo haciendo clic en "**tienda en línea**" en tu administrador de shoperti, accediendo a **menús** y configurando tu **página** de términos y condiciones por ejemplo como parte del menú del **footer** de tu tienda.

#### Meses sin intereses con Conekta

Poder recibir pagos a **meses sin intereses** es una forma de pago que te permite ofrecer una promoción a tu cliente para cobrar en **pagos divididos en mensualidades sin generar intereses**. A ti te permite recibir el monto total de venta en la cuenta bancaria que hayas indicado al momento de registrarte, menos comisión de meses sin intereses en una sola exhibición, además podrás incrementar ventas de un ticket alto gracias a la comodidad de pagarlas a un plazo y el banco se encargará de cobrar al tarjetahabiente en el lapso establecido.

Estas promociones consisten en que el cliente adquiera productos o servicios con una tarjeta de crédito mexicana hasta en **3, 6, 9 o 12 pagos fijos y sin intereses**.

Cuando un cliente concreta una compra a Meses Sin Intereses, el banco toma el monto total de la compra de la línea de crédito del cliente y lo divide por el número de meses de la promoción. A partir de ese momento, empezará a generar cargos mensuales por la cantidad correspondiente sin cobrar ningún tipo de interés al tarjeta habiente.

Conforme el cliente vaya pagando la mensualidad correspondiente, el banco informará en el estado de cuenta del cliente el detalle de la compra así como la mensualidad que está pagando.

Existen montos mínimos de cada transacción en base del plazo seleccionado, se indican a continuación:

[![Conketa](/img/help/settings/single/meses-sin-intereses-1.jpg){.img-responsive}](/img/help/settings/single/meses-sin-intereses-1.jpg)

Para conocer más sobre la **guía de meses sin intereses de Conekta** ingresa a: [https://www.conekta.io/es/guias/meses-sin-intereses/introduccion](https://www.conekta.io/es/guias/meses-sin-intereses/introduccion)

Para poder ofrecer meses sin intereses con **Conekta** en tu tienda de **Shoperti**, lo único que tienes que hacer es **activar el plazo de meses sin intereses** que deseas ofrecer.

Finalmente haz clic en **activar método** y ¡listo! ya puedes ofrecer **meses sin intereses** con **Conekta** en tu tienda de **Shoperti**.

[![Conketa](/img/help/settings/single/meses-sin-intereses-2.jpg){.img-responsive}](/img/help/settings/single/meses-sin-intereses-2.jpg)

Para más información acerca de cómo integrar Conekta con tu tienda de Shoperti, visita los siguientes links:

*   [Para ofrecer a tus clientes pagos en OXXO con efectivo y SPEI](https://www.conekta.io/es/docs/plugins/shoperti/pagos-offline)
*   [Para aceptar pagos con tarjetas de crédito y débito por medio de Conekta](https://www.conekta.io/es/docs/plugins/shoperti)
