
# Guía básica de OPSEC y Anonimato Digital

Si quieres crear una identidad falsa en internet, lo primero a tener en cuenta, es por qué lo haces y de quién te proteges; una ex loca, un script kiddie, espionaje corporativo, una agencia de Ciberinteligencia...

Teniendo claro lo anterior, debemos entender que dependiendo de el nivel de privacidad y anonimato que busquemos, usaremos unos métodos u otros, escarbaremos más en la extensa capa de OPSEC más o menos, todo depende de ti. En esta guía, explicaré las consideraciones básicas para obtener una identidad lo suficientemente anónima como para combatir técnicas de OSINT sofisticadas.

***Esta guía ha sido basada en varios documentos y libros relacionados con el tema, algunos conceptos de esos recursos han sido tomados y escritos de una manera más concisa para mejorar la dinámica y la practicidad de estos, básicamente voy al grano.***

---
# Índice

1. Anonimato general

	1. [Búsqueda segura en internet](#búsqueda-segura-en-internet)
	2. [Contraseñas y 2FA](#contraseñas-y-2fa)
	3. [Correo electrónico seguro](#correo-electrónico-seguro)
	4. [VPNs y la red en general](#vpn-y-la-red-en-general)
	5. [Almacenamiento Seguro](#almacenamiento-seguro)
	6. [Pagos Anónimos](#pagos-anónimos)
	7. [Filtraciones de datos](#filtraciones-de-datos)

2. Creación de tu identidad anónima digital

	1. [Elección de los datos para tu identidad](#elección-de-los-datos-para-tu-identidad)
	2. [Estilometría](#estilometría)
	3. [Perfil biométrico](#pefil-biométrico)
	4. [Finanzas seguras](#finanzas-seguras)
	5. [Uso de números virtuales](#uso-de-números-virtuales)

# Anonimato general
## Búsqueda segura en internet

La mayoría de navegadores y buscadores no sirven en cuanto a privacidad, parece una competencia por quién consigue recolectar y transmitir más información de los usuarios simultáneamente, por ejemplo, Chrome.

- **Chrome** obtiene ingresos a costa de de trackear a los usuarios y sobreexplotar a publicidad el navegador; constantemente recolecta y transmite tus datos. Chrome prioriza el uso de DNS de Google para que estos puedan ver tus dominios visitados

Principalmente recomiendo el uso de **Firefox**, pero hay gente que no le gusta y puede insistir en el uso de un navegador basado en Chromiun, en este caso recomendaría el uso de **Brave**. No es por que sea el mejor navegador del mundo sino porque es la mejor opción dentro de los basados en Chromiun. Brave insiste en que ha quitado completamente la recolecta y transmisión de información la cual viene por defecto en navegadores Chromiun, lo cual puede ser cierto, pero se ha enfrentado a algunas polémicas anteriormente relacionadas con la privacidad de sus usuarios.

En cuanto al buscador por defecto, personalmente prefiero DuckDuckGo, Google manda información sobre tus búsquedas, la almacena, y crea un perfil basado en esas búsquedas con el que luego te mandará publicidad y demás mierdas.

## Contraseñas y 2FA

Puntos a tener en cuenta en este apartado: 

- **Memorización mínima**: es importante no memorizar tus contraseñas, esto se ve relacionado con el hecho de que tus contraseñas seguirán patrones fáciles de descubrir. Por ejemplo, te llamas Juan Pablo, tus contraseñas son: juanpablo2001fcb juanpablo2001insta juanpablo2001twt.... (a parte que depender únicamente de la memorización podría pasarte factura a largo plazo)

- **Usar un gestor de contraseñas**: 

	- **Online**: permiten la sincronización automática entre dispositivos (pc, móvil, ordenador), actualizaciones en tiempo real, y una integración fluida en la web. Sin embargo requieren tu absoluta confianza en el proovedor. **Bitwarden**
	- **Offline**: Permiten mantener el control total de tus contraseñas sin enviarlas a la nube, mediante una sincronización manual. Máximo aislamiento pero puede ser menos conveniente, sin embargo, personalmente esta es la que yo uso. **KeePass**

- **Cambiar gradualmente tus contraseñas**: se recomienda que cada cierto tiempo las cambias, no hace falta que cambies todas y tampoco por periodos cortos de tiempo, solo cuando veas que ya llevas demasiado tiempo. También podrías comprobar si han sido filtradas en la web https://haveibeenpwned.com 


## Correo Electrónico seguro

El email tradicionalmente no se creo con la intención de ser privado o seguro. Los proovedores tradicionales (Google o Microsoft) pueden leer y almacenar todos tus mensajes, ya que mantienen las claves de cifrado y no usan encriptación de extremo a extremo. Estos proovedores entregarán todos tus datos si una fuera de la autoridad se lo pide. También existe del problema de que estos servicios son muy susceptibles a brechas de información

##### Recomendaciones

Yo personalmente uso **Protonmail** extremadamente seguro, privado, anónimo. Recuerdo que hubo una polémica acerca de este servicio, sin embargo, esta polémica no tiene ni pies ni cabeza, en ella se criticaba y cuestionaba la privacidad de Proton pero esto fue porque la persona la cual sufrió esta invasión de privacidad (me parece que fue un ciberdelincuente, no sé al 100% la noticia) fue por tener un correo de recuperación posiblemente proveniente de servicios como Google o Microsoft. Proton OBVIAMENTE debe tener acceso a conocer tu correo de recuperación.

##### Consideraciones

- Si envías información desde un servicio seguro a un servicio que no lo es, esta información se verá expuesta cuando llegue al destinatario.
- Si optas por un plan de pago en Proton o servicios similares, podrás obtener una variedad de posibilidades de privacidad y bueno, quizá te interese.


## VPN y la red en general

Preferiblemente usa ProtonVPN, eso es todo lo que te puedo decir acerca de las VPNs, en general los servicios Suizos brindan una excelente privacidad, y en particular ProtonVPN tiene políticas de privacidad muy sólidas. 

NordVPN es basura, UrbanVPN también.

El router de tu ISP es basura. Tiene backdoors, firmware inseguro y demás mieras.

## Almacenamiento seguro

Aunque pienses que tu dispositivo es seguro por el simple hecho de que para desbloquearlo necesitas una contraseña, estás totalmente equivocado, si alguien tiene acceso a tu disco duro no sería una tarea difícil desbloquearlo. Por eso se recomienda el cifrado de la unidad al completo, puedes hacer esto con VeraCrypt.

VeraCrypt cifrará tu unidad con el tipo de encriptación que elijas, personalmente yo uso SHA-256 pero puedes usar la que tu prefieras.

## Pagos anónimos

No hace falta decir que uses crypto en medida de lo posible, en concreto Monero. Esta criptomoneda es extremadamente privada, fue creada con esa intención; oculta el remitente, el destinatario y el importe de la transacción.

Utiliza un exchange P2P como BitValve, HodlHodl, o LocalCoinSwap, te permiten comprar crypto sin KYC. Después de comprar una crypto mas transparente como Litecoin o Bitcoin puedes usar Trocador para cambiarla por Monero y enviar los fondos a tu monedero personal.

## Filtraciones de datos

Se filtran datos todos los días, por eso debes estar preparado para esto, solo existen dos tipos de empresas: las que han sido hackeadas y las que lo serán.

Puedes comprobar si tus datos han sido comprometidos en la web https://haveibeenpwned.com

---

# Creación de identidad anónima digital

## Elección de los datos para tu identidad

Es importante que los datos que elijas tengan correlación, la creación de una nueva identidad digital no consta solo en que se oculte tu verdadera identidad, sino en que esta nueva identidad parezca real, para hacer esto puedes usar la web https://fakenamegenerator.com, luego aplica esto en tus nombres de usuario y más cosas que veremos adelante en esta guía

## Estilometría

La estilometría es un método muy utilizado por compañías internacionales, agencias de inteligencia y demás para trackear tu identidad a través de tu manera de escribir, si les dijeras a tus amigos que tuvieran una conversación contigo a través de una cuenta falsa, después de un rato podrías llegar a detectar quién es quién, o por lo menos a alguno de ellos, esto por su manera de expresarse. Si tú eres capaz de hacer esto, imagina un software especializado, una IA... deberás adaptar tú manera de escribir a la manera de escribir de la persona que elijas como nueva identidad, por ejemplo si tu identidad OPSEC es un señor de 40 años no puedes seguir hablando como un chaval de 23... 

Sin embargo, por mucho que te esfuerces, la clave no está solo en tu manera de expresarte; signos de puntuación, comas o el tamaño de los mensajes también pueden hacer que te detecten. Es importante que evites tener conversaciones a tiempo real y la escritura lo máximo posible, con el tiempo podrán relacionarte con tu identidad real o por lo menos detectar que la identidad que usas es falsa

## Perfil biométrico

A parte de la estilometría, también tenemos el problema de que se podría detectar tu velocidad de escritura, tus ppm, puedes solucionar esto copiando y pegando del bloc de notas, pero esto solo es la punta del iceberg de tu perfil biométrico...

También pueden detectar similitudes entre dispositivos de tus identidades, así como tiempos de sesión, para tu identidad OPSEC podrías optar por usar un portátil viejo, y no ser demasiado obvio con tus tiempos de sesión, dejar la sesión abierta tiempo de más... Usa tu cabeza, piensa en todas las posibilidades de rastreo

## Finanzas seguras

No hace falta decir que si quieres pasar desapercibido no debes gastar dinero de manera exagerada y deliberada en todo lo que se te ocurra, mantener un perfil bajo te ayudará en el futuro, incluso si no tratas de esconderte, hay mucha gente mala en el mundo. 

En lugar de gastar a lo grande, integre estos fondos en su vida diaria de forma sutil. Haga pequeñas mejoras discretas en sus condiciones de vida o compre artículos relacionados con el trabajo que se mezclen con sus gastos habituales. Utilice efectivo en la medida de lo posible para evitar crear un rastro de papel y opte por recibos sencillos en lugar de facturas.

## Numeros virtuales

Usa un número virtual siempre que sea necesario, pero ojo, siempre que sea necesario, podrías ser rastreado por la empresa que te lo otorga, por lo que evita usar este tipo de servicios lo máximo posible.
