
**Domain description:**

```
Este dominio cubre todas los fundamentos de ciberseguridad, es en efecto notas 101 en el tema.
```

**Knowledge Area:** [[Area - Labor]]


> [!NOTE] Index
> 1. [[#Privacidad y Anonimato]]
> 	1. [[#TOR]]
> 	2. [[#VPN]]
> 	3. [[#TAILS]]
> 	4. [[#Emails]]
> 	5. [[#Manejo y distribución de archivos]]
> 	6. [[#Encriptado]]
> 2. Next 

## Privacidad y Anonimato

#### TOR

Conocida comúnmente como TOR (The Onion Router - Enrutador Cebolla), funciona empleando una serie de conexiones cifradas que pasan a través de múltiples servidores operados por voluntarios, o **nodos**, alrededor del mundo. Cada nodo quita una capa de cifrado, revelando el siguiente destino, similar a las capas de una cebolla, de ahí el nombre. Este proceso hace extremadamente difícil para cualquiera rastrear el origen o destino de los datos, mejorando la privacidad y el anonimato del usuario. Al **rebotar el tráfico a través de una red descentralizada**, TOR ayuda a los usuarios a evadir la censura, la vigilancia y otras formas de monitoreo en línea.

**Navegador TOR**

Para descargar el navegador TOR para un sistema Linux basado en Debian, sigue estos pasos:

- Descarga el archivo adecuado para tu sistema en este [link](https://www.torproject.org/download/languages/).
- Usa el comando **cd** para navegar al directorio de descargas.
- Ejecuta el siguiente comando:

```
./start-tor-browser.desktop --register-app
```

**Verifica si estás conectado exitosamente a la red onion**

Busca en el navegador TOR:

```
check.torproject.org
```

**Eludiendo la censura de TOR**

Para evadir la censura de TOR, nuestro mejor recurso es un puente y un transporte conectable. Cuando hablamos de un **puente**, nos referimos a nodos cebolla no públicos. Por otro lado, usamos transportes conectables porque algunos ISP (Proveedores de Servicio de Internet) van más a fondo e identifican y administran tu tráfico para saber cómo se supone que se vea con el fin de bloquearte el acceso a TOR. El transporte conectable ocultará tu tráfico para que parezca tráfico "normal".

*Ten en cuenta que este método ralentizará considerablemente tu conexión*

Procedimiento:

- Ve a los puentes [link](https://bridges.torproject.org/options)
  - O envía un correo a bridges@torproject.org
    - Si usas este método, también obtén el transporte por correo electrónico.
- Presiona el botón para "obfs4" y luego **Obtener Puentes**
- Copia las líneas del puente
- Ve a Navegador TOR/Configuración/Conexión
- En "Agregar un puente nuevo" selecciona "Seleccionar un puente integrado"
- Pega el puente

Si no te obligan a usar el último método manual pero quieres mantenerte privado al conectarte a TOR, revisa la sección de [VPN](Area%20-%20Labor.md#VPN)

Una vez que hayamos terminado de configurar los últimos pasos, queremos finalizar la configuración de TOR, sigue estos pasos:

- Asegúrate de que TOR esté en su última versión haciendo clic en "buscar actualizaciones"
- Ve a "Privacidad y Seguridad / Historial" y marca "Siempre usar el modo de navegación privada"
- En "Protección contra contenido engañoso ..." marca "Bloquear contenido peligroso y engañoso" y "Bloquear descargas peligrosas"
- **No uses el navegador en pantalla completa, esto puede filtrar el tamaño de tu monitor o laptop, etc.**

**¿Cuál es el nivel de seguridad en TOR?**

En pocas palabras, cuanto más alto esté el nivel de seguridad, menos funciones tendrán habilitadas los sitios web. Por lo tanto, algunos sitios web no funcionarán, pero serás más seguro, más privado y más anónimo.

Te recomendamos que pruebes la seguridad del rastreo web por el sitio web:

```
coveryourtracks.eff.org
```

Uno de los resultados más importantes para la seguridad de TOR es que, según la última prueba de la organización, la opción más baja es más segura que la configuración de seguridad media, sin embargo, te recomendamos una vez más que uses la opción más segura.

Si quieres aprender más sobre cómo te pueden identificar, consulta la documentación relacionada con la **Teoría de la Información**.

#### VPN

**VPN** significa *Red Privada Virtual*, en términos simples una VPN funciona como un túnel inicial que envuelve tu tráfico normal y lo cifra. Esto tiene beneficios como:

- Capa adicional de cifrado.
- Más privacidad y anonimato.
- Eludir la censura.
- Protección contra hackers.

Qué tener en cuenta al usar una VPN:

- Básicamente estamos poniendo a un intermediario en nuestra red, así que usa una **VPN de confianza**.
- *Si el producto es gratis, entonces tú eres el producto*... **evita los proveedores gratuitos** por favor.
- Asegúrate de que **no guarden registros** (a nadie le gusta un impostor).
- Usa **HTTPS EN TODAS las paginas**
- (Opcional) Paga en cryptomonedas.

#### TAILS

Una de los mayores factores de riesgo de usar TOR en Windows, OSX o Linux, es que esencialmente los sistemas operativos comparten y recolectan datos nuestros con tal de mejorar la UX, sin embargo tales datos pueden ser usados para desanonimizar a una persona, estos datos son compartidos a través del Internet directamente sin el uso de TOR de por medio.

Es ahora donde entra TAILS, el cual es el acronimo para **T**he **A**mnesic **I**ncognito **L**ive **S**ystem TAILS es un OS que correrá directamente desde una unidad booteable (como una USB); todo el tráfico de sistema que corra o se ocasione en TAILS será pasando por TOR, adicionalmente, TAILS solamente tiene interacción con la RAM en lo que a memoria respecta, por lo cual podemos decir que TAILS ...

- No deja huellas o rastros
- Es privado y anónimo 
- Corre completamente desde una unidad portable

Al momento de correr TAILS tenemos una pantalla de inicio, la cual recomendamos mantener en los parámetros por default y únicamente revisar las configuraciones avanzadas si es que queremos desactivar el Internet, activar una cuenta de admin para esa sesión o desanonimizar nuestra MAC adress (esto solo en caso que nuestra red tenga una whitelist y solo puedan conectarse ciertos dispositivos)

**Persistencia en TAILS**

La persistencia en TAILS nos dará la capacidad de guardar archivos dentro del OS, el almacenamiento de la computadora quedará intacto, pues usa el espacio restante de la USB, adicionalmente, el volumen persistente es encriptado con LUKS con una frase de segurida personal y en cada booteo, tenemos la opcion de desbloquear o no el volumen de almacenamiento. 

Por la manera en la que TAILS esta configurado, este tiene ciertas restricciones a nivel del kernel para programas como TOR Browser, de tal manera, que el programa tiene únicamente acceso a un solo directorio en el OS (Dos si cuentas uno persistente y otro con amnesia).

#### Emails

Al interactuar en la red existen momentos en donde la prioridad es proteger nuestra identidad en línea, registrarnos en servicios sin revelar información personal, mantener una comunicación segura y privada y/o evitar el rastreo y la vigilancia en línea. 

Para ello los siguientes conceptos son relevantes:

**Identidad fake anónima**:
 * Una identidad completamente falsa creada para interactuar en línea sin revelar tu identidad real.
 * Para proteger tu privacidad en foros, redes sociales o cualquier plataforma donde no quieras ser identificado.

**Cuentas email temporales:**
 * Direcciones de correo electrónico que se autodestruyen después de un tiempo o una vez que se ha utilizado.
 * Para registrarte en servicios sin dejar rastro, recibir correos de verificación o evitar spam.

**Proveedores privados de email:**
 * Servicios de correo electrónico que priorizan la privacidad y la seguridad del usuario, ofreciendo funciones como cifrado end-to-end y políticas de no registro de datos.
 * Para una comunicación segura y privada, especialmente si manejas información sensible.

**Proveedores de email de la darknet:**
 * Servicios de correo electrónico accesibles a través de la darknet, diseñados para un alto nivel de anonimato.
 * Para una comunicación extremadamente privada, especialmente si necesitas ocultar tu identidad por completo.

#### Manejo y distribución de archivos 

Uno de los pilares respecto al manejo de archivos y privacidad seria la elimination apropiada de los metadatos, todos los archivos tienen metadatos, estos nos hablan de ...
- El creador
- Programa usado para crearlo
- Hora y fecha de la creación 
- etc


#### Encriptado 