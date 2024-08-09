# Guía de OSINT v2

---

## Índice

---

➤ 1. Introducción a OSINT
- ¿Qué es OSINT?

➤ 2. Identificación de usuarios
- Utilizando Google Dorks 
- Utilizando instantusername

➤ 3. Identificación de dominios
- Uso de la herramienta censys
- Uso de la herramienta shodan
- Uso de sublist3r para listar subdominios
- Correos electrónicos  asociados 

➤ 4. Extracción de metadatos
- Uso de exiftool
- Uso de FOCA

➤ 5. Información sobre IP
- Uso de la api Ipinfo 
- Uso de nmap

➤ 6. Correos electrónicos
- epieos

➤7. Filtraciones de datos
- Bot de OSINT Industries
- Bot de data doki
- Dehashed

➤ 8. Anonimato y privacidad
- Uso de correos temporales
- Uso de una VPN segura
- Técnicas para no ser rastreado

---

## 1. Introducción a OSINT

- OSINT (Open Source Intelligence) es la recopilación y análisis de información obtenida de fuentes abiertas, osea recursos que están públicos alrededor de internet, como medios de comunicación, redes sociales... en esta guía enseñaré la forma optimizada de llevar a cabo OSINT, utilizando herramientas que nos permiten hacer la búsqueda de los recursos mucho mas rápida y eficiente.

## 2. Identificación de usuarios

### Google Dorking

- ➤ Google Dorking, a esto se le llama a utilizar términos de búsqueda avanzados dentro del buscador de Google, os enseñaré algunos útiles:

	1.  el principal es `"query"`, (lo de query es una palabra random, la importancia es las comillas), cuando un texto va entre comillas, Google buscará ÚNICA y EXCLUSIVAMENTE contenido que contenga el texto tal cual está entre las comillas, esto se hace debido a que muchas veces buscas un usuario y Google te enseña personas que no tienen nada que ver y muchas veces ni se parecen los nombres de usuario... XD.
	2. site:query.com, con este dork le decimos a Google que solo queremos que nos salga información proveniente de un sitio web en concreto, por ejemplo site:instagram.com (Podemos combinar ambos dorks si así lo queremos)

> Otra manera de crear un dork es usando IA, en este caso podemos usar la IA https://dorkgpt.com/

---

### Instant username

- Para esto usaremos la web de https://instantusername.com/ y escribiremos el nombre de usuario que queremos identificar en la gran cantidad de redes sociales disponibles

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271417636101689385/image.png?ex=66b74372&is=66b5f1f2&hm=17dfe8b9428fd8e90720925bdf78b26db49ea3d6a9fb27b08f2ee8cc9ce5c6dd&=&format=webp&quality=lossless&width=500" >

> Podéis usar herramientas como theHarvester o sherlock para esta labor, pero en mi preferencia instanusername es mejor por su rapidez, facilidad de uso y alta enumeración de redes sociales.


---

## 3. Identificación de dominios

### Censys

- **Uso de la herramienta Censys**: Para usar esta herramienta, primero deberemos ir a la página oficial de esta, la cual es: https://search.censys.io/ una vez aquí, escribiremos el dominio (o IP) en la barra de búsqueda, y estos son los resultados que obtendremos: 

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271416791104622703/Captura_de_pantalla_2024-08-09_121413.png?ex=66b742a8&is=66b5f128&hm=2c51fb267be10280298d59736d0aa80f8125104c8996a78b6f2e97c351ebb98f&=&format=webp&quality=lossless&width=500" width=500px>

- **Campos interesantes**
	+ `Autonomous System`: Información sobre la red o el proovedor de servicios de internet del dominio
	+ `Locations`: Localizaciones en las que está hosteado el dominio
	+ `Services Names`: Los servicios que están disponibles (http, ssh, ftp...) para el dominio
	+ `Ports`: Puertos abiertos del dominio
	
---

### Shodan

- **Uso de la herramienta shodan**:  Shodan es un motor de búsqueda especializado que permite a los usuarios encontrar dispositivos conectados a Internet, como servidores, cámaras, routers, y sistemas de control industrial. Para usar shodan primero entraremos en está página:   https://www.shodan.io/ y nos registraremos

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271416781906640968/Captura_de_pantalla_2024-08-09_122311.png?ex=66b742a6&is=66b5f126&hm=e1ba48e705c97e5a1345ddca0575572a0280c706559a97046e1c1dc539609fa2&=&format=webp&quality=lossless&width=500">

- En el buscador de shodan podemos usar dorks, algo similar a lo de Google, podemos por ejemplo usar un dork para filtrar por ciudad:

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271416775849938974/Captura_de_pantalla_2024-08-09_122415.png?ex=66b742a5&is=66b5f125&hm=51f0f62057a1c0c3604d762223e7b0b472fe9a409fc1b02934c3e6c55451187c&=&format=webp&quality=lossless&width=500">

> En este caso he filtrado por la ciudad de Barcelona usando el dork `city:`

- Mas dorks de shodan aquí: https://github.com/lothos612/shodan

---

### Sublit3r

- Nos clonaremos el repositorio de https://github.com/aboul3la/Sublist3r haciendo `git clone https://github.com/aboul3la/Sublist3r` en nuestra terminal, o de lo contrario descargando el zip, luego descargaremos las librerías necesarias, dentro de la carpeta escribiremos `pip install -r requirements.txt` para descargarlas (Es necesario tener Python instalado). Finalmente ejecutaremos el script con:  `python3 sublist3r.py -d dominio.com` o también:   `python sublist3r.py -d dominio.com`

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271416767964774472/Captura_de_pantalla_2024-08-09_122816.png?ex=66b742a3&is=66b5f123&hm=0e98257af88e65f529efdf11d6c7f7dfa1562d7d3ce0666d4947f16c3dd023b1&=&format=webp&quality=lossless&width=501&height=525">

- En este ejemplo hice una prueba con tinder.com 

---

### Correos electrónicos asociados

- Entraremos a la web https://www.phonebook.cz (debemos estar registrados con Intelx), luego usaremos la opción "Emails Adresses" y finalmente escribiremos nuestro dominio

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271416757667631227/Captura_de_pantalla_2024-08-09_123106.png?ex=66b742a0&is=66b5f120&hm=605a0a297ce86141fcd346c8982017953d7618e59feb1212d3e70465961f1d15&=&format=webp&quality=lossless&width=500" width=500px>

> Nota: también podemos usar la opción `Domains` y efectuar una búsqueda por subdominios similar a Sublist3r (pero puede ser incluso mas efectiva)

---

## 4. Extacción de metadatos

### Exiftool

- Nos clonaremos el repositorio https://github.com/exiftool/exiftool como hicimos con el sublist3r pero sin descargar librerías, ya que es un ejecutable, simplemente haremos `./exiftool archivo`

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271416746972155925/Captura_de_pantalla_2024-08-09_123449.png?ex=66b7429e&is=66b5f11e&hm=8792f5aa6d75e462fc2c06fefd85f6d87f313f69134e2c045d9506af40bed554&=&format=webp&quality=lossless&width=1485&height=630">

> Otra herramienta que os puede servir es FOCA, pero no la agregué porque está mas orientado a OSINT de empresas o entidades públicas.

---

## 5. Información de IPS

### Uso de la api de Ipinfo

- Para usar esta api iremos a la web https://www.ipinfo.io escribiremos una IP y nos dará información sobre esta

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271418382079754354/image.png?ex=66b74424&is=66b5f2a4&hm=cc12e5bdae5db215c08da8b41667e8f0dd1c4199f4ef5538400198c8f4af9713&=&format=webp&quality=lossless&width=1407&height=1249">

---

### Uso de nmap

- Para usar nmap primero deberemos descargarlo desde la web oficial https://nmap.org/download.html luego iremos a la terminal y ejecutaremos `nmap --help` para ver las múltiples opciones que tiene

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271418797781160027/image.png?ex=66b74487&is=66b5f307&hm=429d6a5ef15ca84de0e50a9fae3bc945284b13cdeb682e71668e6ed2c19a422d&=&format=webp&quality=lossless&width=1707&height=1357">

- Me podría tirar hasta mañana hablando de sus parámetros, así que aquí tienes una guía de nmap: https://lacriptadelhacker.wordpress.com/2020/01/30/guia-definitiva-de-nmap/

---

## 6. Identificación de correos electrónicos

### Epieos

- Para esto iremos a la web de https://epieos.com/?q=testtest12%40gmail.com&t=email y buscaremos un correo electrónico

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271419431821770803/image.png?ex=66b7451e&is=66b5f39e&hm=b00993166440ab73e4201aa13ada2f3356c77714c9afc34c745ed2591b000d06&=&format=webp&quality=lossless&width=2148&height=721">

---

## 7. Filtraciones de datos

### Bot de OSINT Industries

- Para esto le hablaremos al bot de Telegram: https://t.me/Breach_Forums_Bot?start=DcGJJXG

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271420134925275196/image.png?ex=66b745c6&is=66b5f446&hm=7bb44546b0a1e50cfb9817e60372683d537d99e56a78c7e64314b7186d5ff273&=&format=webp&quality=lossless&width=1272&height=1357" >

- Hay un montón de mirrors de este  bot, son todos iguales

> Para cargar tus créditos deberas pedirle al bot que te envie la billetera a la que mandar la cripto, una vez que la envies a la billetera que te de el bot la cantidad exacta que te pide se te recargarán.

---

### Bot de naz api

- Este no tan conocido bot que no es el mismo de siempre utiliza otra base de  datos y lo que le mandes te enviará los datos encontrados en un archivo txt https://t.me/DataDokiBot

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271420652724686909/image.png?ex=66b74641&is=66b5f4c1&hm=f6683befb35484bdd5b265d2fa3d5e7d618b7f5a5c49c0256e47e5a66a971e8e&=&format=webp&quality=lossless&width=822&height=226">

> Cabe recalcar que este bot te ofrece una cantidad de créditos gratuitos muy muy baja, al ser mas potente necesitarás comprar créditos de su tienda, aunque realmente no son tan caros si solo quieres unas cuantas búsquedas, los pagos se efectúan igual que el de OSINT Industries

---

### Dehashed

- Es ir a la página de https://dehashed.com/ y comprar una licencia, no está mal pero es de pago, a mi preferencia los bots están bastante mejor en cuanto a calidad/precio y calidad bruta de información.

---

## 8. Anonimato y privacidad

### Uso de correos temporales

- Hay muchas páginas que proporcionan esto, te hablaré de tempmail (https://temp-mail.org/en/), entrás aquí y se te otorgará un correo temporal que podrás usar por un tiempo limitado

> <img src="https://media.discordapp.net/attachments/1271315816675016769/1271421687249895454/image.png?ex=66b74738&is=66b5f5b8&hm=7fdb6f3cb4b0c4cc01631a8185d912a94a6148083d025b4fb50be730954c6f48&=&format=webp&quality=lossless&width=483&height=525">

> Algunos os preguntaréis **¿Para qué quiero correos temporales?** Bueno, son realmente útiles para cuando quieres registrarte en un sitio sin importancia y de manera rápida

---

### Usar una VPN segura

- **PROTON VPN** Es la VPN mas segura o de las que más seguras son, esto principalmente se debe a que su sede está en Suiza. Recomiendo completamente usarla. Nord VPN o Urban VPN están bien pero no protegen tu información tanto como lo hace Proton VPN

---

### Técnicas para no ser rastreado

- Enumeraré unas cuantas ténicas para esto
	+ **No usar siempre el mismo nombre de usuario**: podrías ser rastreado si siempre usas tu mismo nombre de usuario, un hacker podría descubrir información confidencial si te encuentra en algunas redes sociales como Instagram o Facebook, o ve tus tuits públicos
	+ **No tener cuentas públicas**: es importante conocer los riesgos de tener una cuenta pública en algun sitio que contenga información personal sobre ti, lo mejor es que en tus redes privadas tengas tu cuenta en privado y tengas a tus amigos y familiares, ten cuidado con la gente que aceptas, recuerda que cuando les aceptas les das vía libre a conocer toda la información que proporcionas en esa red social sobre tí.
	+ **Usar una VPN**: Obviamente no estarás usando una VPN constantemente, pero es importante que cuando vayas a entrar a sitios raros o estés haciendo algo en lo que no te interesa ser rastreado, mínimo usa una VPN en esas situaciones.
	+ **Usar una máquina virtual cuando sea necesario**: Muchas veces nos descargamos archivos de dudosa procedencia por la curiosidad de saber lo que contienen y esto muchas veces lleva a descargar Spyware y que nuestros datos acaben en los bots de telegram... XD o en el ordenador de algún Indú, para esto, cuando creas que un programa es inseguro o de poca fiabilidad, ten una máquina virtual (VMWare o VirtualBox) preparada, unos minutos de más podrían salvar todos tus datos.
	
