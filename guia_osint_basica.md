# GUÍA DE OSINT BÁSICA


## ÍNDICE

➤ 1. Introducción al OSINT y la recopilación de información

- ¿Qué es el OSINT?
- ¿Qué es el Doxxing?

➤ 2. Tipos de OSINT

- OSINT a Individuales o Empresas

➤ 3. Guía OSINT a Individuales (Básico)

- Métodos de identificación de nombre de usuario
	+ Googe Dorking
	+ Dónde está registrado un nombre de usuario
	+ Obtener información de un usuario de discord
	
- Métodos de identificación de correo electrónico
	+ Donde está registrado un correo electrónico 
	
- Datos empresariales
	+ Información laboral de una persona
	

- Información sobre una IP
	+ Geolocalización de una IP 
	+ Mas información
	+ IP Grabbing (Obtener la IP de alguien)
	
- Información de imágenes
	+ Búsqueda inversa de imágenes
	+ Geolocalización de imágenes

- Filtaciones de datos
	+ Donde buscar
	
---

## 1. Introducción


> Antes de nada, esta guía está pensada para personas que inician en el mundillo, por lo que no tocaré el tema de usar la terminal como puede ser
		   al momento de usar herramientas como nmap para puertos, o theHarvester y Sherlock para búsqueda de usuarios, intentaré hacerla sencilla y para
		   todo público, en la siguiente parte de la guía complementaré con cosas algo mas avanzadas para poder conseguir información de una persona.
	


- El Doxxing significa encontrar información personal y confidencial de una persona, emails, contraseñas, direcciones, tarjetas de crédito... normalmente para hacerlo se hace uso de alguna metodología OSINT, OSINT es como se le llama a la investigación de información que proviene de fuentes abiertas, esto quiere decir información pública. Que sea pública no significa que sea de fácil acceso, por buscar en Google "Contraseña de Juan" no vas a encontrar nada... para esto se usan ciertas herramientas que nos facilitan el proceso de recolección de información las cuales nombraré y enseñaré a usar a lo largo de esta guía.

---

## 2. Tipos de OSINT

- Con "Tipos de OSINT" me refiero a que tipo de objetivo tenemos al frente, puede ser tanto una empresa como una persona, en esta guía solo enseñaré OSINT a individuales. Próximamente puede que enseñe el de empresas, aunque muchas veces se pueden usar ambos en un mismo objetivo, todo depende del 
contexto.

---

## 3. Guía de OSINT a Individuales

---

### 3. 1 Métodos de identificación de usuario

- ➤ **Google Dorking**, a esto se le llama a utilizar términos de búsqueda avanzados dentro del buscador de Google, os enseñaré algunos útiles: 
	1. el principal es `"query"`, (lo de query es una palabra random, la importancia es las comillas), cuando un texto va entre comillas, Google buscará **ÚNICA y EXCLUSIVAMENTE** contenido que contenga el texto tal cual está entre las comillas, esto se hace debido a que muchas veces buscas un usuario y Google te enseña personas que no tienen nada que ver y muchas veces ni se parecen los nombres de usuario... XD. 
	2. `site:query.com`, con este dork le decimos a Google que solo queremos que nos salga información proveniente de un sitio web en concreto, por ejemplo site:instagram.com (Podemos combinar ambos dorks si así lo queremos)
> Otra manera de crear un dork es usando IA, en este caso podemos usar la IA https://dorkgpt.com/


- ➤ Para saber donde se ha registrado un nombre de usuario podemos usar varias herramientas, una de ellas pueden ser el script de Sherlock, theHarvester… pero si no te apetece usar scripts, tienes una web para esto: [Instantusername](https://instantusername.com/#/) 

- ➤ Si el usuario que queremos está en discord, podemos ver algo de información sobre él directamente con su Nick de discord usando la página [Namedc](https://namedc.org)

---
 		
### 3. 2 Métodos de identificación de correo electrónico

➤ Para esto podemos usar la web https://epieos.com/ que nos dirá donde está registrado un correo electrónico.

---

### 3.3 Datos empresariales

- ➤ Para esto podemos buscar a la persona en LinkedIn, InfoJobs, o también si es de España podemos buscarle en https://www.datoscif.es/empresa

---

### 3.4 Información sobre una IP

- ➤ Podemos usar la web https://www.ipinfo.io
- ➤ También podemos usar la API de https://www.ip-api.com (A mi gusto me ha dado bastante buena precisión en cuanto a geolocalización)
- ➤ También podemos ver que puertos tiene abiertos haciendo uso de https://www.shodan.io (también podemos usar nmap)
- ➤ Podemos obtener la IP de alguien mandándole un enlace, para esto podemos usar la web de https://grabify.link/, una vez que entremos podemos configurar nuestro enlace, para esto pondremos la url donde serán redirigidos los que entren (grabify nos creará un enlace para robar la infode las IP, una vez que entren serán automáticamente redirigidos a la página que queramos por ejemplo Google pero en ese proceso en el dashboard de grabify ya tendremos la información). Podemos también (y debemos) modificar la IP que grabify nos da para que sea lo mas creible posible.

---

### 3.5 Imágenes

- ➤ Podemos buscar fotos de personas para ver si nos sale mas información sobre ellos haciendo uso del buscador Bing o Google en la opción de búsqueda por imagen, también la aplicación móvil PhotoSherlock o usando https://tineye.com/
- ➤ También podemos buscar la geolocalización (bastante precisa después de un rato que la probé) https://geospy.ai/

---

### 3.6 Filtraciones de datos


- ➤ Para consultar filtraciones de datos podemos usar la web dehashed, lamentablemente es de pago, pero hay foros donde se suben bases de datos muchas veces gratuitas como BreachForums y podemos consultar allí. También hay algunos bots de Telegram con mucha información pero esos los dejaré para la siguiente parte de la guía