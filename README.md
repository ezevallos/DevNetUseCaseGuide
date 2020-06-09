# Guía de Casos de Uso - DevNet

Esta guía fue desarrollada con el apoyo de David Fernández (Cisco), Franco Ramírez (Cisco) y Matt Denapoli (Cisco).

<div id='toc'/>

# Tabla de contenidos
1. [Introducción - Cisco DevNet](#intro)
2. [Lab 1: Cómo usar Python para obtener un inventario de red en Meraki.](#para1)
3. [Lab 2: Cómo usar Python para mostrar información de dispositivos de una red conectados a un DNA-Center](#para2)
4. [Lab 3: Cómo usar Python y Flask para implementar un ChatBot en Webex Teams](#para3)
5. [Lab 4: Reconocimiento de imágenes mediante un comando de voz.](#para4)

<div id='intro'/>

# Cisco DevNet 
_Cisco Developer’s Network_ o _Cisco DevNet_ es nuestra comunidad de práctica para desarrolladores y profesionales de TI que buscan escribir aplicaciones y desarrollar integraciones con productos, plataformas y APIs de Cisco. A continuación, navegaremos por los componentes principales que conforman la plataforma de Cisco DevNet, a la que podemos acceder mediante la dirección: [https://developer.cisco.com/](https://developer.cisco.com/).
![DevNet](https://i.ibb.co/dDrKd7d/DN-IN-1.png)

## Start Now
Aquí ([https://developer.cisco.com/startnow/](https://developer.cisco.com/startnow/)) encontraremos una lista curada de contenidos para empezar nuestro viaje, es el lugar ideal para aquellos que desean tomar el primer paso en programación, o llevar sus habilidades al siguiente nivel. Es el lugar para tener una experiencia de aprendizaje guiada y aplicada, en las plataformas y tecnologías de Cisco.
![DevNetStartNow](https://i.ibb.co/BCqvtR7/DN-IN-2.png)

## Learning Tracks
Aquí ([https://developer.cisco.com/learning/tracks](https://developer.cisco.com/learning/tracks)) encontraremos una ruta guiada de aprendizaje en tecnologías de Cisco selectas. Están basadas en los DevNet Learning Labs, un track está conformado por módulos, que a su vez están conformados por los learning labs. Algunos módulos se enfocan en conocimientos generales de programación, redes y otros temas.

 - [https://developer.cisco.com/learning/modules](https://developer.cisco.com/learning/modules)
 - [https://developer.cisco.com/learning/labs](https://developer.cisco.com/learning/labs)
![DevNetLearningTracks](https://i.ibb.co/kg9shVs/DN-IN-3.png)

## Video-Course
Aquí ([https://developer.cisco.com/video/net-prog-basics/](https://developer.cisco.com/video/net-prog-basics/)) encontraremos un inicio al viaje hacia la programabilidad de la red con este video curso dirigido por expertos. Tenemos 6 módulos, cada uno con lecciones que incluyen API y ejemplos de código que puede usar en su propio entorno de desarrollo para seguir junto con los videos.
![DevNetVideoCourse](https://i.ibb.co/HDDrpmG/DN-IN-4.png)

## Sandbox
Aquí ([https://developer.cisco.com/site/sandbox/](https://developer.cisco.com/site/sandbox/)) encontraremos un entorno donde ingenieros, desarrolladores, administradores de red, arquitectos o cualquier otra persona que desee desarrollar / probar las API, controladoras, equipo de red, herramientas de colaboración de Cisco y más, pueden hacerlo de forma gratuita. Ejecute su código contra la infraestructura en vivo 24x7, el acceso es gratuito, a una variedad de laboratorios; elija entre entornos virtualizados, simuladores y hardware real.
![DevNetSandBox](https://i.ibb.co/fnJctHw/DN-IN-5.png)

## Code-Exchange
Aquí ([https://developer.cisco.com/codeexchange/](https://developer.cisco.com/codeexchange/)) encontraremos un conjunto de repositorios de código en línea, públicos en GitHub, que han sido seleccionados y están relacionados con todas las áreas de tecnología de Cisco. En Code Exchange, contamos con cientos de repositorios de código, puede encontrar código creado y mantenido por equipos de ingenieros de Cisco, colaboradores de la comunidad, socios del ecosistema, comunidades de tecnología y de código abierto y desarrolladores individuales. Los miembros de la comunidad DevNet de Cisco pueden usar este código para impulsar su desarrollo de aplicaciones e integraciones usando las API de Cisco.
![DevNetCodeExchange](https://i.ibb.co/t3ctc3j/DN-IN-6.png)

## Ecosystem-Exchange
Aquí ([https://developer.cisco.com/codeexchange/](https://developer.cisco.com/codeexchange/)) encontraremos una plataforma para conectar el ecosistema global de los socios de Cisco que están creando soluciones y servicios utilizando las API de Cisco, a los clientes que buscan aprovechar o integrar las soluciones existentes para impulsar los resultados comerciales.
![DevNetEcosystemExchange](https://i.ibb.co/0MVWTKL/DN-IN-7.png)

[↑](#toc)
<div id='para1'/>

# Lab: Cómo usar Python para obtener un inventario de red en Meraki

### (Duración - 45 minutos)

## Objetivos
 - **Parte 1: Aprender a navegar en DevNet para encontrar recursos valiosos**
 - **Parte 2: Utilizar scripts de automatización para realizar pruebas y aprender**

## Contexto / Escenario
**_Cisco Meraki_** es la solución de red gestionada en nube de **Cisco**. Ofrece un portafolio de productos de infraestructura de red que incluye Access points, Enterprise switches, routers e incluso cámaras. Su versátil modelo de gestión basado en nube permite administrar la topología desde cualquier lugar del mundo, y provisionar equipos con tan solo una conexión a internet, y una fuente de poder. Este caso de uso sirve para crear un inventario de la red de forma automatizada. En el día a día de un administrador de red, esta es una tarea muy común pues cada dispositivo tiene una dirección IP única, y estas pueden variar bien sea porque se asignan dinámicamente, o porque se realiza algún cambio en la topología. Realizar este proceso de forma repetitiva es simple, pero puede consumir tiempo y el error humano puede causar complicaciones. Este laboratorio utiliza las herramientas que nos ofrece **_Cisco DevNet_** para automatizar tareas frecuentes que realizan los ingenieros de red, en particular obtener un inventario de los equipos que conforman una topología **_Cisco Meraki_**. Se explica cómo navegar dentro de la plataforma de nuestra comunidad de práctica **_DevNet_** para realizarlo, haciendo uso solamente de un navegador web, del **_SandBox Meraki Always On_** en caso no contemos con una red propia **_Meraki_**, y de un interpretador de Python bien sea en el entorno local de desarrollo o en su defecto podemos utilizar uno basado en la web.
![LabMerakiInventory](https://i.ibb.co/31fNcwR/DM-CM-1.jpg)
[Video Corto sobre Meraki]((https://www.youtube.com/watch?v=xKEIVLYGWWA))

## Recursos requeridos
 - Acceso a Internet
 - Navegador web
 - Cuenta de **_Cisco DevNet_**

## Parte 1: Navegar por los recursos necesarios en DevNet
### Paso 1: Echamos un vistazo en DevNet Automation Exchange
DevNet Automation Exchange es una biblioteca donde encontraremos casos de uso donde la programabilidad ha sido utilizada para automatizar tareas comunes en networking. La comunidad de desarrolladores de **_Cisco_** llamada **_DevNet_**, actualiza y crea continuamente código para inspirar a la comunidad a seguir desenvolviéndose en la creación de software orientado a las redes.

 1. Abrir el navegador, acceder a [https://developer.cisco.com](https://developer.cisco.com), e ingresar con su cuenta.
![DevNetLogin](https://i.ibb.co/FbJ3SWt/DN-DM-1.png)
 2. En la barra superior, dirigirse _Discover_ → **Inspire** → _DevNet Automation Exchange_. ![DevNet Sandbox](https://i.ibb.co/Lrf0X6y/DN-SB.png)

### Paso 2: Aprendemos a navegar entre los casos de uso
Para hacer más simple el proceso, se han establecido estados en los que se podría encontrar el desarrollador. Estos son Caminar – Correr – Volar, donde el primero representa casos más fáciles de implementar y el posterior, casos más complicados. Por otro lado, los casos se encuentran clasificados dependiendo del ciclo de vida en el que se encuentra la red, día 0, día 1, día 2, o día N.

Adicionalmente, se puede filtrar basado en el escenario, dominio, y producto.

3. Al ingresar al _Automation Exchange_, hacer click en el botón de _View all use cases_ para acceder a la biblioteca completa de casos de uso.
![DevNetAutomationExchange](https://i.ibb.co/ftwPDNp/DN-DX-1.png)
 4. Entre las opciones de filtrado, elegir el producto **Cisco-Meraki**
![DevNetAutomationExchangeMeraki](https://i.ibb.co/RgYDvw8/DN-DX-2.png)

### Paso 3: Identificar el caso de uso para automatizar la creación de un inventario de red.
Dentro de _DevNet_ existe **_DevNet Code Exchange_**, que compendia repositorios de proyectos en _GitHub_ con los que podemos descubrir, aprender, construir y colaborar, de forma que podamos impulsar nuestro trabajo en plataformas, productos, APIs, y SDKs de Cisco.
 5. El caso de uso que utilizaremos lleva el nombre de "_Manage Multiple Meraki organizations_". Hacemos click en el caso de uso.
![DevNetAutomationExchangeManageMultipleMerakiOrgs](https://i.ibb.co/hdjmksH/DN-DX-3.png)
 6. Leemos la breve descripción, para entender el caso de uso, se trata de una serie de scripts en Python que nos permitirán realizar tareas comunes del administrador de una red **_Meraki_**, de forma automatizada. Luego damos click en el botón “_See code on Code Exchange”_ para entrar al **_DevNet Code Exchange_**.
![DevNetAutomationExchangeCodeExchange](https://i.ibb.co/4dZ9r68/DN-DX-4.png)
 7. En el **_Code Exchange_**, encontraremos información acerca de cada uno de los scripts de automatización que se encuentran disponibles para nuestra utilización. Los invitamos a leer cada una de las descripciones, en particular nos enfocaremos en el fichero que lleva el nombre “**_listip.py_**”. Este código crea una lista de todos los números seriales, modelos y LAN IP, de dispositivos que forman parte de una red **_Meraki_** para una organización. Hacemos click en el botón “_View on GitHub”._
![DevNetCodeExchangeAutomationScripts](https://i.ibb.co/LtnxNgj/DN-DX-5.png)

### Paso 4: Acceder y utilizar el repositorio en GitHub
GitHub es un sistema de gestión de proyectos y control de versiones de código, así como una plataforma de red social diseñada para desarrolladores. Permite trabajar en colaboración con otras personas de todo el mundo, planificar proyectos y realizar un seguimiento del trabajo.

 1. Hemos accedido al repositorio donde podremos encontrar todos los scripts de automatización. Como lo mencionamos en el taller ETW: Experimenting with REST APIs, **_GitHub_** es una plataforma y comunidad de práctica donde los desarrolladores archivan su código en la nube. Entre los ficheros, buscaremos el que lleva por nombre ”**_listip.py_**“ y accedemos a este.
![DevNetCodeExchangeGitHubAutomationScripts](https://i.ibb.co/Z2MnMZw/DN-DX-6.png)
 2. En el fichero, buscamos la opción para visualizar el código en “_raw_”.
![DevNetCodeExchangeGitHubAutomationScriptsRaw](https://i.ibb.co/C6bd8km/DN-DX-7.png)
 3. De esta forma podemos obtener la versión del código que podemos copiar (Ctrl – A y Ctrl – C) y pegar (Ctrl – V) al interpretador de Python de nuestra preferencia.
![DevNetCodeExchangeGitHubAutomationScriptsListIPRaw](https://i.ibb.co/x8g1wtr/DN-DX-8.png)
 4. En caso no contemos con un interpretador en nuestro entorno de desarrollo, podemos utilizar uno basado en web, un ejemplo es repl.it ([https://repl.it/@enaard/Python-3](https://repl.it/@enaard/Python-3)) donde podemos interpretar Python3. Pegamos el código que obtuvimos en el paso anterior.
![DevNetCodeExchangeListIPReplIt](https://i.ibb.co/qnN1jjT/DN-DX-9.png)
 5. Realizaremos un cambio en la última línea, para eso necesitaremos los detalles de la red **_Meraki_** que se busca inventariar. En caso no contemos con una red de este tipo, utilizaremos el SandBox que podremos encontrar en **_DevNet_**.

## Parte 2: Utilizar el SandBox Meraki Always On
### Paso 1: Acceder y utilizar el SandBox Meraki Always On
**_DevNet_** nos provee muchos SandBoxes. Estos son entornos virtuales que emulan equipos físicos o redes donde podemos aprender a realizar configuraciones como la que intentamos efectuar. En este caso en particular, haremos uso del **_SandBox Meraki Always On_** que nos permite recrear una topología de red de **_Cisco Meraki_** en caso no contemos con una para realizar el laboratorio.
 1. Regresamos a la página principal de **_Cisco DevNet_** y navegamos a _Discover_ → _**Code**_ → _Sandbox Remote Labs_ donde encontraremos más información acerca de los Sandbox. Cómo utilizarlos, si se trata de un _Sandbox_ que siempre se encuentra activo, o si es necesario reservarlo por cierta cantidad de tiempo, caso en el que además debemos esperar cierto tiempo para que _DevNet_ prepare los recursos que utilizaremos. Es importante mencionar que todos los recursos que encontraremos en _DevNet_ son totalmente libres para los miembros de nuestra comunidad. Para acceder, debemos crearnos una cuenta, o utilizar nuestro Cisco ID en caso ya contemos con uno. Los alumnos de Cisco Networking Academy tienen una pre-cuenta de _DevNet_ utilizando sus credenciales NetAcad.
![DevNet Sandbox](https://i.ibb.co/Lrf0X6y/DN-SB.png)
 2. Aquí encontraremos la respuesta a muchas preguntas acerca de estos entornos virtuales, donde desarrolladores, ingenieros, administradores de red, arquitectos, y todos podemos desarrollar y probar las APIs, controladoras, equipos de red y suites de colaboración de Cisco.  Podremos correr nuestro código en infraestructura que se encuentra activa 24/7, en una variedad de laboratorios de acceso libre, y escoger entre entornos virtualizados, simuladores, e infraestructura física. Nos dirigimos al catálogo completo haciendo click en “_View all Sandboxes_”.
![All DevNet Sandboxes](https://i.ibb.co/hH8DkjN/DN-SB-2.png)
![Buscador Sandboxes](https://i.ibb.co/jvBXdxS/DN-SB-3.png)
 3. El catálogo cuenta con 70 _Sandboxes_ distintos. Para filtrar, podemos hacerlo por tipo, por categoría, por status, o podemos simplemente hacer click en la búsqueda, y tipeamos la palabra “**_Meraki_**” para encontrar el que vamos a usar.
![Sandbox Meraki Always-On](https://i.ibb.co/MfcwkGM/DN-SB-4.png)
 4. Encontraremos tres _Sandboxes_ de **_Meraki_**, el que utilizaremos se llama “**_Meraki Always On_**” y se trata de una red de prueba **_Meraki_** a la que podemos acceder en cualquier momento para realizar pruebas. En este _Sandbox_ podemos encontrar los detalles importantes que nos faltan para que el script funcione correctamente. En primer lugar, las credenciales de acceso al Dashboard API, Username: [devnetmeraki@cisco.com](mailto:devnetmeraki@cisco.com), Password: ilovemeraki, y por otro lado, el API Key que utilizaremos es 6bec40cf957de430a6f1f2baa056b99a4fac9ea0.
![SandBox Meraki Always-On Overview](https://i.ibb.co/zfKNwzv/DN-SB-5.png)

### Paso 2: Acceder al Dashboard API de Meraki
Meraki Dashboard API es una interfaz para que el software interactúe directamente con la plataforma en la nube de Meraki y los dispositivos administrados por Meraki.
 1. Luego, nos dirigimos a [http://dashboard.meraki.com/](http://dashboard.meraki.com/) donde encontraremos el último detalle que nos falta, el nombre de la organización. Damos click en “Log in to personal account” e ingresamos las credenciales que nos otorga el Sandbox.
![SandBox Meraki Always-On Dashboard](https://i.ibb.co/FsHjc6x/DN-SB-6.png)
![SandBox Meraki Always-On DashboardAccess](https://i.ibb.co/RS4RHTT/DN-SB-7.png)
 2. Para encontrar el nombre de la organización, nos dirigimos a _Organization_ → _Configure_ → _Settings_ encontraremos que el primer campo nos provee el nombre “_DevNet Sandbox_”.
![SandBox Meraki Always-On Dashboard Orgs](https://i.ibb.co/dBzG7Wy/DN-SB-8.png)

### Paso 3 (Opcional): Utilizar mi propia red Meraki
En caso contemos con una red de Cisco Meraki, también podemos utilizar el script. Para esto será necesario obtener un API Key desde nuestro propio Dashboard, y el nombre de la organización, como lo hicimos previamente. A continuación, detallamos cómo realizarlo:

 1. Para acceder a la API, primero habilite la API para su organización en Organization > Settings > Dashboard API access. Después de habilitar acceso mediante API, vaya a la página de mi perfil para generar una clave API. La clave API está asociada con una cuenta de administrador del Tablero.

## Parte 3: Modificar el script para nuestro caso de uso
### Paso 1: Ingresar el API Key y el nombre de la organización
Para lograr que funcione nuestro script, debemos modificar la última línea que es la que se encarga de ejecutar el código en su integridad.

 1. Esta es “main(sys.argv[1:])”, la cual está pidiendo los argumentos API Key y Organization Name. Previamente obtuvimos esta información, y es por eso que reemplazaremos esta línea de código con
```python
main(['-k','6bec40cf957de430a6f1f2baa056b99a4fac9ea0', '-o', 'DevNet Sandbox'])
```
donde le estamos pasando los parámetros mencionados. En caso estemos corriendo el script para nuestra propia red, mantenemos los parámetros ‘-k’ y ‘-o’, y donde hemos colocado el API Key y el nombre de organización del Sandbox, ingresaremos la información obtenida en el paso 3 de la parte 2. Procedemos a correr el script.
![SandBoxMerakiAlways-OnReplIt](https://i.ibb.co/stRg3jP/DN-SB-9.png)
 2. Finalmente, obtenemos el resultado esperado, una lista de equipos que conforman la topología de red, junto con la información pertinente.

[↑](#toc)
<div id='para2'/>

# Lab: Mostrar información de los dispositivos de una red conectados a un DNA-Center

### (Duración - 45 minutos)

## Objetivos

 - **Parte 1: Aprender a navegar en DevNet para encontrar recursos valiosos**
 - **Parte 2: Utilizar scripts de automatización para realizar pruebas y aprender**

## Contexto / Escenario
**_Cisco Digital Network Architecture – Center (DNA Center)_** es la arquitectura de Cisco para redes empresariales. Proporciona un enfoque abierto, extensible e impulsado por software que hace que la red sea más simple de administrar y más ágil y receptiva a las necesidades del negocio. Este caso de uso sirve para tener visibilidad de los dispositivos conectados a la red de forma automatizada. En el día a día de un administrador de red, esta es una tarea muy común pues. Realizar este proceso de forma repetitiva es simple, pero puede consumir tiempo y el error humano puede causar complicaciones. Este laboratorio utiliza las herramientas que nos ofrece **_Cisco DevNet_** para automatizar tareas frecuentes que realizan los ingenieros de red, en particular . Se explica cómo navegar dentro de la plataforma de nuestra comunidad de práctica **_DevNet_** para realizarlo, haciendo uso solamente de un navegador web, de un **_SandBox Always On_** que invocamos directamente desde el código, y de un interpretador de Python bien sea en el entorno local de desarrollo o en su defecto podemos utilizar uno basado en la web.
![DNAC-Python](https://i.pinimg.com/originals/43/bc/17/43bc1772bd748f043cfd1bd7d91ec2c4.png)

## Recursos requeridos
 - Acceso a Internet
 - Navegador web
 - Cuenta de **_Cisco DevNet_**

## Parte 1: Navegar por los recursos necesarios en DevNet
### Paso 1: Echamos un vistazo en DevNet Automation Exchange
DevNet Automation Exchange es una biblioteca donde encontraremos casos de uso donde la programabilidad ha sido utilizada para automatizar tareas comunes en networking. La comunidad de desarrolladores de **_Cisco_** llamada **_DevNet_**, actualiza y crea continuamente código para inspirar a la comunidad a seguir desenvolviéndose en la creación de software orientado a las redes.

 1. Abrir el navegador, acceder a [https://developer.cisco.com](https://developer.cisco.com), e ingresar con su cuenta.
![DevNetLogin](https://i.ibb.co/FbJ3SWt/DN-DM-1.png)
 2. En la barra superior, dirigirse _Discover_ → **Inspire** → _DevNet Automation Exchange_. ![DevNet Sandbox](https://i.ibb.co/Lrf0X6y/DN-SB.png)

### Paso 2: Aprendemos a navegar entre los casos de uso
Para hacer más simple el proceso, se han establecido estados en los que se podría encontrar el desarrollador. Estos son Caminar – Correr – Volar, donde el primero representa casos más fáciles de implementar y el posterior, casos más complicados. Por otro lado, los casos se encuentran clasificados dependiendo del ciclo de vida en el que se encuentra la red, día 0, día 1, día 2, o día N.

Adicionalmente, se puede filtrar basado en el escenario, dominio, y producto.

 1. Al ingresar al _Automation Exchange_, desplazarse hacia abajo hasta la sección de _Cisco Infraestructure_, pasar el cursor por encima del botón de **_Cisco DNA Center_** y dar click en el botón _‘see use cases’_ para acceder a la biblioteca de casos de uso de **_DNA-C_**.
![DNACUseCases](https://i.ibb.co/Hg00kZq/DN-SB-10.png)

### Paso 3: Identificar el caso de uso para automatizar el listado de dispositivos conectados al DNA-C
Dentro de _DevNet_ existe **_DevNet Code Exchange_**, que compendia repositorios de proyectos en _GitHub_ con los que podemos descubrir, aprender, construir y colaborar, de forma que podamos impulsar nuestro trabajo en plataformas, productos, APIs, y SDKs de Cisco.

 1. El caso de uso que utilizaremos lleva el nombre de “_Display device information from Cisco DNA Center_”. Hacemos click en el caso de uso.
![DNACUseCaseAutoScript](https://i.ibb.co/G369CML/DN-SB-11.png)
 2. Leemos la breve descripción para entender el caso de uso, se trata de un script en Python que nos permitirá obtener información de los dispositivos conectados a una red mediante el **_Cisco DNA Center_**, de forma automatizada. Luego damos click en el botón “_See code on Code Exchange”_ para entrar al **_DevNet Code Exchange_**.
![DNACUseCaseCodeExchange](https://i.ibb.co/QrrHdXZ/DN-SB-12.png)
 3. En el **_Code Exchange_**, encontraremos información acerca del script de automatización que se encuentra disponible para nuestra utilización. Aquí están las instrucciones para hacer correr el script en los distintos sistemas operativos, para clonar el repositorio de github, la referencia de documentación del API, y finalmente un snippet de lo que obtendremos al ejecutar. Hacemos click en el botón “_View on GitHub”._
![DNACUseCaseGitHubCodeExchange](https://i.ibb.co/Vq2HHqZ/DN-SB-13.png)

### Paso 4: Acceder y utilizar el repositorio en GitHub
GitHub es un sistema de gestión de proyectos y control de versiones de código, así como una plataforma de red social diseñada para desarrolladores. Permite trabajar en colaboración con otras personas de todo el mundo, planificar proyectos y realizar un seguimiento del trabajo.

 1. Hemos accedido al repositorio donde podremos encontrar todos los scripts de automatización. Como lo mencionamos en el taller ETW: Network Programmability, **_GitHub_** es una plataforma y comunidad de práctica donde los desarrolladores archivan su código en la nube. Entre los ficheros, buscaremos el que lleva por nombre “**_get_dnac_devices.py_**” y accedemos a este.
![DNACAutoScriptGitHubRepo](https://i.ibb.co/mB9KdHy/DN-SB-14.png)
 2. En el fichero, buscamos la opción para visualizar el código en "_raw_".
![DNACAutoScriptGitHubRaw](https://i.ibb.co/T8n7HQd/DN-SB-15.png)
 3. De esta forma podemos obtener la versión del código que podemos copiar (Ctrl – A y Ctrl – C) y pegar (Ctrl – V) al interpretador de Python de nuestra preferencia.
![DNACAutoScriptGitHubRawCode](https://i.ibb.co/pWPv785/DN-SB-16.png)
 4. En caso no contemos con un interpretador en nuestro entorno de desarrollo, podemos utilizar uno basado en web, un ejemplo es repl.it ([https://repl.it/@enaard/Python-3](https://repl.it/@enaard/Python-3)) donde podemos interpretar Python3. Pegamos el código que obtuvimos en el paso anterior. Este código se autentica en un **_DNA Center_**, y procede crear una tabla con los dispositivos que se encuentran conectados. Sin embargo, aún no contamos con el entorno necesario para el laboratorio. Este se implementará utilizando un **_Sandbox_**, que instanciaremos mediante un fichero llamado “**_env_lab.py_**”.
![DNACAutoScriptReplIt](https://i.ibb.co/z2LH5Wx/DN-SB-17.png)
 5. Volvemos al repositorio de **Github** y esta vez buscamos el fichero llamado “**_env_lab.py_**”.
![DNACAutoScriptGitHub](https://i.ibb.co/2sZttcq/DN-SB-18.png)
 6. En el fichero, buscamos la opción para visualizar el código en “_raw_”.
![DNACAutoScriptGitHubRaw](https://i.ibb.co/pvHnTFB/DN-SB-19.png)
 7. De esta forma podemos obtener la versión del código que podemos copiar (Ctrl – A y Ctrl – C) y pegar (Ctrl – V) al interpretador de Python de nuestra preferencia.
![DNACAutoScriptGitHubRawCode](https://i.ibb.co/NFyTFjs/DN-SB-20.png)
 8. En repl.it, creamos un nuevo fichero, al que llamaremos “**_env_lab.py_**”, y es aquí donde pegamos el contenido que copiamos en el paso anterior.
![DNACAutoScriptReplIt](https://i.ibb.co/dKnpbSf/DN-SB-21.png)
 9. Habiendo establecido el entorno al que accederá nuestro fichero principal, volvemos a este, y lo ejecutamos. Observamos que luego de instalar los módulos necesarios para el correcto funcionamiento del script, este nos arroja una tabla en la que figura el host, la plataforma, el software que utiliza, la versión que se encuentra ejecutando, y el tiempo que tiene en marcha.
![DNACAutoScriptReplIt](https://i.ibb.co/y4jmShp/DN-SB-22.png)
![DNACAutoScriptReplIt](https://i.ibb.co/d0mShXk/DN-SB-23.png)
 10. (Opcional) Este caso es particularmente útil pues podemos encontrar casos donde nuestro cliente cuenta con más de un **_DNA Center_**, o podemos contar con varios clientes, cada uno con su **_DNA Center_**. Podemos utilizar el mismo script cambiando sólo el entorno en el que se ejecuta. Para esto volvemos al fichero “**_env_lab.py_**”, y modificamos el nombre del **_Sandbox_** que se está utilizando. En lugar de que el script indique **_sandboxdnac.cisco.com_**, colocaremos un número 2 luego de “**_sandboxdnac_**”, de forma que figure **_sandboxdnac2.cisco.com_**. Corremos el script principal (**_get_dnac_devices.py_**) nuevamente, y observamos el resultado.
![DNACAutoScriptReplIt](https://i.ibb.co/VmdyPg6/DN-SB-24.png)
![DNACAutoScriptReplIt](https://i.ibb.co/9p4F4Lv/DN-SB-25.png)
Notamos en esta última captura de pantalla que los dispositivos son diferentes, pues se trata de un **_DNA Center_** distinto al primero. Pensemos en la posibilidad de tener muchos más clientes para los que deseamos obtener la misma información, y mediante una lógica básica podemos crear un script que nos entregue de forma automatizada los dispositivos de todos los **_DNA Center_** que podamos tener a nuestra disposición.

[↑](#toc)
<div id='para3'/>

# Lab: Implementación de un ChatBot de Webex Teams con Python y Flask.

## Objetivos
En este laboratorio, aprenderá a ejecutar su propio bot de Webex Teams siguiendo los siguientes pasos:

- Crear una cuenta bot en https://developer.webex.com
- Ejecutar una aplicación de bot Webex Teams de muestra en su PC
- Registrar un webhook con el servicio API de Webex Teams
- Exponer su bot a internet para que pueda recibir notificaciones entrantes de webhook de Webex Teams

Finalmente, chatear con su nuevo amigo:
![AwesomeBot](https://developer.cisco.com/learning/posts/files/collab-spark-botl-itp/assets/images/Objectives_chat.png)

## Pre-requisitos
Necesitará una cuenta de usuario de Webex Teams para completar este laboratorio:
1. Vaya al sitio web de desarrolladores de Webex Teams
2. Si aún no tiene una cuenta, haga clic en Registrarse, luego pruebe Meetings Free y siga las instrucciones
3. Inicie sesión con sus nuevas credenciales

## Step 1: Crear una cuenta bot
1. Inicie sesión en '[Webex for Developers](https://developer.webex.com/)' y abra la entrada del menú "My Webex Teams Apps" debajo de su avatar. Esto lo llevará a la página "[Mis aplicaciones](https://developer.webex.com/my-apps)":
![BotAccount](https://developer.cisco.com/learning/posts/files/collab-spark-botl-itp/assets/images/Step1_my_apps.png)
2. Haga clic en el botón **Crear una nueva aplicación** y elija "Crear un bot":
![CreateBot](https://developer.cisco.com/learning/posts/files/collab-spark-botl-itp/assets/images/Step1_bot.png)
```git
Esta acción muestra el [Formulario de creación de bot] (https://developer.webex.com/my-apps/new/bot) que se muestra en la siguiente ilustración.
```
1. Complete un nombre y un identificador de correo electrónico único para su bot.
2. Elija un color de cara para su bot entre los propuestos rojo, amarillo o verde, y agregue una breve descripción:
![NewBot](https://developer.cisco.com/learning/posts/files/collab-spark-botl-itp/assets/images/Step1_my_awesome_bot.png)
3. Haga clic en Agregar Bot para crear su cuenta Bot
4. Una vez que la página se actualiza, se muestran los detalles de su bot.
5. Desplácese hacia abajo hasta la parte inferior de la página para revelar el token de acceso de su bot
6. Copie / pegue el token de su bot en un lugar seguro (o simplemente mantenga esta pestaña abierta), ¡ya que no se volverá a mostrar! Lo usará más adelante en este laboratorio.
![BotToken](https://developer.cisco.com/learning/posts/files/collab-spark-botl-itp/assets/images/Step1_token.png)
**Nota: el token de acceso de un Webex Teams Bot dura 100 años. Si alguna vez pierde o revela el token de su bot, simplemente regrese a la página de detalles de su bot y regenere un nuevo token de acceso. El token emitido previamente será revocado automáticamente**
6. En este punto, su bot se puede agregar a cualquier espacio de Webex Teams especificando su correo electrónico, al igual que con un usuario normal.
Vaya a su cliente favorito de Webex Teams y cree un nuevo espacio 1-1 con su bot como participante.
![ChatwithBot](https://developer.cisco.com/learning/posts/files/collab-spark-botl-itp/assets/images/Step1_new_room_share.png)

[↑](#toc)
<div id='para4'/>

# Lab: Reconocimiento de imágenes mediante un comando de voz. Utilice las *APIs* de *Cisco Meraki*, *Imagga* y *Google Actions* para analizar la captura de una cámara de Meraki, mediante un comando de voz en un dispositivo *Android* con *Google Assistant* 

Este laboratorio se desarrolló con el apoyo de Matt Denapoli (Cisco).

## Introducción
En este laboratorio obtenemos un *snapshot* de una cámara *Cisco Meraki*, haciendo uso del *Dashboard API*. Luego, envíamos la imagen a un software de reconocimiento de imágenes llamado *Imagga*, cuyo *API* es de uso abierto. Finalmente, utilizamos la *API* de *Google Actions* para que nos lea las características de la imagen en voz alta, y nos muestre la imagen; mediante un comando de voz de *Google Assistant*.


## Objetivos

Al completar este laboratorio, estará familiarizado con el uso básico de las *APIs* de *Cisco Meraki*, *Imagga* y *Google Actions*, y además:

 - Obtener la captura de una cámara Meraki, mediante el *Dashboard API*.
 - Utilizar el URL de la imagen, para obtener el archivo donde esta se encuentra.
 - Enviar esta imagen al software de reconocimiento, llamado *Imagga*, mediante su *API*
 - Modularizar el código para llamarlo desde nuestro *web server*.
 - Crear un *web server Flask* que sirva las características e imagen obtenidas en el script previo
 - Publicar nuestro proyecto a *Heroku* para acceder a él desde una dirección web.
 - Configurar *Google Actions* para llamar a nuestro *web server* mediante un comando de voz en *Google Assistant*, usando *DialogFlow*.

## Pre-requisitos

 - Manejo de ***Python*** y sus librerías, en particular ***Flask*** para desplegar *web servers*
 - Cuenta de ***DevNet*** para utilizar el ***Sandbox Meraki Always-On***.
 - Cuenta de ***GitHub*** y un conocimiento básico de contol de versiones, según lo descrito en [Introducción a Git](https://developer.cisco.com/learning/tracks/devnet-beginner-es/fundamentals-es/intro-to-git-es/step/1).
 - [***Git Bash***](https://git-scm.com/downloads) instalado en nuestro entorno de desarrollo. 
 - Cuenta de ***Imagga*** para contar con un *api_key* y *api_secret* y enviar imágenes a reconocer.
 - Cuenta de ***Heroku*** para acceder a nuestro código de ***Python*** desde una URL pública
 - Cuenta de ***Google*** para acceder a ***DialogFlow***

## Acerca de Cisco Meraki

***[Cisco Meraki](https://meraki.cisco.com/)*** es la solución de red gestionada en nube de **Cisco**. Ofrece un portafolio de productos de infraestructura de red que incluye Access points, Enterprise switches, routers, dispositivos de seguridad de red e incluso cámaras. Su versátil modelo de gestión basado en nube permite administrar la topología desde cualquier lugar del mundo, y provisionar equipos con tan solo una conexión a internet, y una fuente de poder.

## Utilizar el ***SandBox Meraki Always-On***

***[DevNet](https://developer.cisco.com/)*** nos provee muchos SandBoxes. Estos son entornos virtuales que emulan equipos físicos o redes donde podemos aprender a realizar configuraciones como la que intentamos efectuar. En este caso en particular, haremos uso del ***SandBox Meraki Always On*** que nos permite acceder a una cámara de ***Cisco Meraki*** en caso no contemos con una para realizar el laboratorio. Esta cámara en particular, se encuentra apuntando a una TV que se encuentra prendida 24/7. Nos dirigimos a la página principal de ***DevNet*** y navegamos a _Discover_ --> _**Code**_ --> _Sandbox Remote Labs_ donde encontraremos más información acerca de los _Sandboxes_. Encontramos información sobre cómo utilizarlos, si se trata de un _Sandbox_ que siempre se encuentra activo, o si es necesario reservarlo por cierta cantidad de tiempo, caso en el que además debemos esperar unos minutos para que _DevNet_ prepare los recursos que utilizaremos. Es importante mencionar que todos los recursos que encontraremos en ***DevNet*** son totalmente libres para los miembros de nuestra comunidad. Para acceder, debemos crearnos una cuenta, o utilizar nuestro ***Cisco ID*** en caso ya contemos con uno. Los alumnos de ***Cisco Networking Academy*** tienen una pre-cuenta de _DevNet_ utilizando sus credenciales NetAcad.

![DevNet Sandbox](https://i.ibb.co/Lrf0X6y/DN-SB.png)
Aquí encontraremos la respuesta a muchas preguntas acerca de estos entornos virtuales, donde desarrolladores, ingenieros, administradores de red, arquitectos, y todos podemos desarrollar y probar las APIs, controladoras, equipos de red y suites de colaboración de Cisco.  Podremos correr nuestro código en infraestructura que se encuentra activa 24/7, en una variedad de laboratorios de acceso libre, y escoger entre entornos virtualizados, simuladores, e infraestructura física. Nos dirigimos al catálogo completo haciendo click en “_View all Sandboxes_”.
![All DevNet Sandboxes](https://i.ibb.co/hH8DkjN/DN-SB-2.png)
![Buscador Sandboxes](https://i.ibb.co/jvBXdxS/DN-SB-3.png)
El catálogo cuenta con 70 _Sandboxes_ distintos. Para filtrar, podemos hacerlo por tipo, por categoría, por status, o simplemente hacer click en la búsqueda, y tipeamos la palabra “**_Meraki_**” para encontrar el que vamos a usar.
![Sandbox Meraki Always-On](https://i.ibb.co/MfcwkGM/DN-SB-4.png)
Encontraremos tres _Sandboxes_ de **_Meraki_**, el que utilizaremos se llama “**_Meraki Always On_**” y se trata de una red de prueba **_Meraki_** a la que podemos acceder en cualquier momento para realizar pruebas. En este _Sandbox_ podemos encontrar los detalles importantes para que el script funcione correctamente. En primer lugar, las credenciales de acceso al Dashboard API, Username: [devnetmeraki@cisco.com](mailto:devnetmeraki@cisco.com), Password: ilovemeraki, y por otro lado, el *API Key* que utilizaremos es 6bec40cf957de430a6f1f2baa056b99a4fac9ea0.

## El script `requirements.txt`
A continuación especificamos las librerías que utilizaremos para este laboratorio de tal forma que se puedan instalar de forma recursiva en el entorno donde tendremos nuestro interpretador de Python.
```python
certifi==2019.11.28
chardet==3.0.4
idna==2.9
requests==2.23.0
urllib3==1.25.8
Flask==1.1.1
Flask-Assistant==0.4.1
Flask-Cors==3.0.8
gunicorn==19.9.0
jsonify==0.5
```

## El script `GetSnap.py`
Nuestro código en ***Python*** va a obtener una captura de la cámara Meraki modelo MV12W, cuyo número serial es el Q2GV-7HEL-HC6C, y se ubica en la red con Id L_566327653141856854 llamada *DNEAlertsNet*. Esta red no la encontraremos dentro de la interfaz del Dashboard API, pero sí estará listada si hacemos las llamadas de **Postman** *Get Organization Id* y *Get Networks Id*, utilizando el *API Key* previamente mencionado. La organización lleva el nombre *DeLab* y su Id es el 681155. Esta cámara ha sido posicionada delante de una TV que se encuentra prendida 24/7, de forma que siempre tiene algo qué mostrar, y su contenido es dinámico.

En primer lugar, debemos especificar las librerías que estaremos utilizando. Estas son *pprint*, *requests* y *json*, las importamos a continuación:
```python
from pprint import pprint
import requests
import json
```
Para obtener una captura de lo registrado en la cámara, debemos hacer uso del *API* de la siguiente forma:
```python
    def setHeaders_meraki():
	    header = {
		    "X-Cisco-Meraki-API-Key":"6bec40cf957de430a6f1f2baa056b99a4fac9ea0",
		    "Accept":"application/json",
		    "Content-Type":"application/json"
		    }
		    return header
	def getSnap(theHeader):
		uri = "https://api.meraki.com/api/v0/networks/L_566327653141856854/cameras/Q2GV-7HEL-HC6C/snapshot?X-Cisco-Meraki-API-Key=6bec40cf957de430a6f1f2baa056b99a4fac9ea0"
		resp = requests.post(uri, headers = theHeader,data={})
		return resp.json()
		
	header = setHeaders_meraki()
	snapshot = getSnap(header)
```
En el código anterior, definimos primero los headers que enviaremos en nuestra llamada al *API* de *Meraki Dashboard*,  a través de la función *setHeaders_meraki*, especificamos el *API Key*, y los parámetros que debe aceptar y devolver nuestra llamada(JSON). Estos parámetros los alimentamos a nuestra función *getSnap*, la cual se encarga de hacer el llamado mediante el método *POST* y devuelve un *JSON* en forma de diccionario que podremos indexar para extraer la URL, `url = snapshot["url"]`.
Para obtener la imagen de la URL, debemos realizar un pequeño artificio:
```python
def get_image(url):
	code = 404
	while code != 200:
		response = requests.get(url)
		code = response.status_code
	return response.content
```
Luego podemos obtener la imagen y asignarla en una variable `image = get_image(url)`. Nuestro código hasta este punto:
```python
from pprint import pprint
import requests
import json

def setHeaders_Meraki():
	header = {
		    "X-Cisco-Meraki-API-Key":"6bec40cf957de430a6f1f2baa056b99a4fac9ea0",
		    "Accept":"application/json",
		    "Content-Type":"application/json"
		    }
		    return header
		    
def getSnap(theHeader):
		uri = "https://api.meraki.com/api/v0/networks/L_566327653141856854/cameras/Q2GV-7HEL-HC6C/snapshot?X-Cisco-Meraki-API-Key=6bec40cf957de430a6f1f2baa056b99a4fac9ea0"
		resp = requests.post(uri, headers = theHeader,data={})
		return resp.json()

def get_image(url):
	code = 404
	while code != 200:
		response = requests.get(url)
		code = response.status_code
	return response.content

header = setHeaders_meraki()
snapshot = getSnap(header)
url = snapshot["url"]
print(40*"-")
print(url)
print(40*"-")
image = get_image(url)
```
### Recapitulemos
Hasta este punto, nuestro código consta de tres funciones. La primera, `setHeaders_Meraki` se encarga de crear un diccionario y asignarlo a la variable header. Este será el *JSON* con el que realizaremos nuestra llamada al *Dashboard API* de *Meraki*. Luego la segunda función, `getSnap`, se encarga de la realización de esta llamada, utilizando el método *POST* del módulo `requests` y de esta forma recibe otro *JSON* como respuesta. Este *JSON* lo almacenamos en forma de diccionario en la variable `snapshot`, y lo indexamos para obtener la URL de la imagen, mediante `url = snapshot["url"]`. Finalmente, la tercera función se encarga de buscar la imagen en la URL mediante el método *GET* y guarda el contenido en la variable `image`.

Habiendo obtenido la imagen, procedemos a enviarla a un software de reconocimiento de imágenes llamado *Imagga*. Esto lo haremos a través de su *API*, para lo cual es necesario crearnos una cuenta. Ingresamos a la dirección [http://imagga.com/](http://imagga.com/)
![SignUp Imagga](https://i.ibb.co/xGz65vT/IG-SU-1.png)
Procedemos a llenar el formulario con los datos apropiados, para este caso de uso sólo es necesario una cuenta gratuita.
![SignUp Imagga Form](https://i.ibb.co/F408zdG/IG-SU-2.png)
Con esto ya podemos acceder al [Dashboard de Imagga](https://imagga.com/profile/dashboard) y aquí encontraremos el *API Key* y *API Secret* necesarios para realizar el reconocimiento de la imagen.
![Imagga API Keys](https://i.ibb.co/gPwMJcx/IG-SU-3.png)
Habiendo obtenido estos parámetros, podemos proceder a realizar el reconocimiento de la imagen. Para esto definiremos las variables `imagga_url`, `api_key` y `api_secret`, y una función llamada `analyze` que se encarga de realizar la llamada mediante el método *POST* y asignarlo a una variable llamada `response`:
```python
imagga_url = 'https://api.imagga.com/v2/tags'
api_key = 'YOUR_API_KEY'
api_secret = 'YOUR_API_SECRET'

def analyze(url, image, key, secret):
	response = requests.post(
		url,
		auth=(key, secret),
		files={'image':image})
	return response

response = analyze(imagga_url, image, api_key, api_secret)
```
Luego podemos indexar las etiquetas de reconocimiento y asignarlo a una variable de la siguiente manera:
`tags = [item['tag']['en'] for item in response.json()['result']['tags']]`
De esta manera, obtenemos una lista ordenada con las etiquetas, que procedemos a transformar en un *string*. Para esto es necesario crear una última función que convierta una lista a un string y acorte la lista luego de cierta cantidad de caracteres sin dejar palabras cortadas o comas flotantes, y lo asignamos a la variable `speech`:
```python
def listToString(s):  
    # initialize an empty string 
    str1 = ""  
    # traverse in the string   
    for ele in s:  
        str1 = str1 + ele + ","
    # cut string without leaving floating characters or slashed words
    str1 = str1[:415]
    while(str1[-1]!=','):
        str1 = str1[:-1]
    str1 = str1[:-1]
    # return string   
    return str1
	
speech = listToString(tags)
```
### Recapitulemos
Hasta este punto, nuestro código obtiene una imagen de la siguiente manera: la función `setHeaders_Meraki`, se encarga de crear un diccionario(*JSON*) y asignarlo a la variable header. Con este *JSON* realizamos una llamada al *Dashboard API* de *Meraki*. Luego la segunda función, `getSnap`, se encarga de realizar esta llamada, utilizando el método *POST* del módulo `requests` y de esta forma recibe otro *JSON* como respuesta. Este *JSON* lo almacenamos en forma de diccionario en la variable `snapshot`, y lo indexamos para obtener la URL de la imagen, mediante `url = snapshot["url"]`. La tercera función, `get_image` se encarga de buscar la imagen en la URL mediante el método *GET* y guarda el contenido en la variable `image`. 
Habiendo conseguido esta imagen, realizamos el análisis apalancando la *API* de *Imagga*. Para esto hemos obtenido un *API_Key* y un *API_Secret* en la web de [*Imagga*](https://imagga.com/), y creamos una función llamada `analyze`, que toma estos parámetros, además de utilizar un endpoint especificado por *Imagga*. Nos devuelve un nuevo *JSON* con la clasificación que realizado de nuestra imagen. Finalmente, la función `listToString` se encarga de convertir la lista de etiquetas que hemos obtenido, en un *String* que podrá enunciar el Asistente de nuestro dispositivo Android. Nuestro código hasta esta etapa es el siguiente:
```python
from pprint import pprint
import requests
import json

#Vars
imagga_url = 'https://api.imagga.com/v2/tags'
api_key = 'YOUR_API_KEY'
api_secret = 'YOUR_API_SECRET'

#Helper functions
def setHeaders_meraki():
	header = {
		"X-Cisco-Meraki-API-Key":"6bec40cf957de430a6f1f2baa056b99a4fac9ea0",
		"Accept": "application/json",
		"Content-Type":"application/json"
	}
	return header

def getSnap(theHeader):
	uri = "https://api.meraki.com/api/v0/networks/L_566327653141856854/cameras/Q2GV-7HEL-HC6C/snapshot?X-Cisco-Meraki-API-Key=6bec40cf957de430a6f1f2baa056b99a4fac9ea0"
    resp = requests.post(uri, headers = theHeader,data={})
    return resp.json()

def get_image(url):
    code = 404
    while code != 200:
        response = requests.get(url)
        code = response.status_code
    return response.content

def analyze(url, image, key, secret):
    response = requests.post(
        url,
        auth=(key, secret),
        files={'image': image})
    return response

def listToString(s):  
    # initialize an empty string 
    str1 = ""  
    # traverse in the string   
    for ele in s:  
        str1 = str1 + ele + ","
    str1 = str1[:415]
    while(str1[-1]!=','):
        str1 = str1[:-1]
    str1 = str1[:-1]
    # return string   
    return str1
    
# Main function
def main():
    header = setHeaders_meraki()
    snapshot = getSnap(header)
    url = snapshot["url"]
    print(40*"-")
    print(url)
    print(40*"-")
    image = get_image(url)
    response = analyze(imagga_url, image, api_key, api_secret)
    pprint(response.json(), indent=2, width=200)
    print(40*"-")
    tags = [item['tag']['en'] for item in response.json()['result']['tags']]
    speech = listToString(tags)
    return (speech, url)

if __name__ == '__main__':
	main()
```
Hasta este punto en nuestro desarrollo, hemos creado un código en *Python* que se encarga de obtener una captura en una cámara Meraki, obtener la imagen que se encuentra en esta URL, y enviarla a un software de reconocimiento de imágenes llamado *Imagga*. Esto lo realiza nuestra función principal llamada `Main`.¡Fantástico! Si han llegado hasta este punto, lo han hecho muy bien. Sin embargo, ahora deseamos poder apalancar esta funcionalidad desde nuestro Asistente de Android, llamado *Google Assistant*. Para lograr esto, será necesario correr un servidor *Flask* haciendo uso de una librería en particular llamada *Flask Assistant* la cual permite la comunicación con asistentes de voz como es *Google Assistant* o *Alexa Skills* por nombrar algunos ejemplos. Este servidor web debemos almacenarlo en un lugar de acceso público en internet, de manera que el *API* de *Google Actions* pueda acceder a él, y para esto utilizaremos *Heroku*. Para crear este servidor, importaremos el script `GetSnap.py`,  por lo que vamos a renombrar la función principal y eliminar las últimas dos líneas del código. Se vería de la siguiente forma (notar que el resto del código se ha omitido y colocado tres puntos "..." para enfocarnos en la parte clave que estamos modificando):
```python
...
	return str1

# return speech function
def return_speech():
    header = setHeaders_meraki()
    snapshot = getSnap(header)
    url = snapshot["url"]
    print(40*"-")
    print(url)
    print(40*"-")
    image = get_image(url)
    response = analyze(imagga_url, image, api_key, api_secret)
    pprint(response.json(), indent=2, width=200)
    print(40*"-")
    tags = [item['tag']['en'] for item in response.json()['result']['tags']]
    speech = listToString(tags)
    return (speech, url)
```
De esta forma, podemos importar el archivo `GetSnap.py` como un módulo en nuestro servidor web *Flask*, y utilizar todas sus funcionalidades. Este nos devuelve una tupla con las etiquetas de categorización en formato *String* y el URL de la imagen.

---
**Nota:**
Es importante que el archivo o fichero `GetSnap.py` se encuentre en el mismo directorio que nuestro servidor web.
---


## El script app.py
Nuestro código debe importar la funcionalidad del script `GetSnap.py` y servirlo desde un *web server* a través de rutas especificadas. Primero es necesario importar las librerías necesarias, y el script previamente mencionado:
```python
from flask import Flask
from flask_assistant import Assistant, tell
from flask_cors import CORS
import GetSnap
``` 
La librería *Flask* nos permite la creación del servidor web en forma local. Por otro lado, la librería *Flask Assistant* habilita el uso de asistentes como *Google Assistant* o *Alexa Skills*, en particular utilizaremos el módulo *tell* que nos devolverá la respuesta en forma enunciada. Adicionalmente, importamos *Flask CORS* que habilita el intercambio de recursos de distintos orígenes. Finalmente, importamos el script `GetSnap.py` que creamos previamente que contiene la lógica para obtener la imagen de la captura y realizar el reconocimiento.
Ahora es necesario crear el aplicativo que se encontrará en el *web server*, mediante la línea de código `app = Flask(__name__)`. Lo configuramos para *Google Actions* con `app.config['ASSIST_ACTIONS_ON_GOOGLE'] = True` y `app.config['INTEGRATIONS'] = ['ACTIONS_ON_GOOGLE']`.  Inicializamos la extensión de *Flask-Cors* con los argumentos por defecto que permite el *CORS* para todos los dominios, en todas las rutas, `cors = CORS(app)`. Inicializamos un objeto de tipo *Assistant* utilizando el *Flask app*, y la ruta a la URL de nuestro *webhook*, `assist = Assistant(app, route='/google')`.
A continuación creamos nuestras rutas: 
- La primera será para propósitos de debugging cuando hacemos una llamada de tipo *GET* al servidor, nos devuelve un mensaje de prueba como "Eureka".
```python
@app.route("/", methods=['GET'])
def main():
	return "Eureka"
```
- La segunda es la principal, utilizaremos el decorador *action* para mapear nuestro *intent* o propósito llamado "*tv-watch*", a la función apropiada. El decorador acepta el nombre de nuestro propósito como parámetro, y hace la función de visor de nuestra acción, cuando recibimos el pedido de *Dialogflow*. La función de acción devolverá un *tell* como respuesta enunciada,  
```python
@assist.action('tv-watch')
def google_tv_watch():
	speech,url = GetSnap.return_speech()
	return tell("I see " + speech[:415]).card(
		text="See...",
		title="Image:",
		img_url=url
	)
```
Hacemos uso de una tarjeta para presentar la información, mostrando las etiquetas como texto, un título y la imagen analizada.
Esta será nuestra función principal, y será un *web server* que se engargue de servir los recursos llamados mediante los *requests* realizados desde el *Google Assistant* a través de *Dialogflow*. Es por esto que incluímos una última línea de código 
```python
if __name__ == '__main__':
	app.run(threaded=True, port=5000)
```
Es decir, nuestro aplicativo estará habilitado para utilizar hilos, y se encontrará disponible en el puerto 5000.
### Recapitulemos
Hasta este punto, nuestro código obtiene la imagen de una cámara *Meraki Vision* utilizando el *Dashboard API* y realiza un análisis mediante el API de *Imagga*, un software de reconocimiento de imágenes. Obtiene el url de la imagen, y las etiquetas del análisis y lo asigna a una tupla que será enunciada y mostrada utilizando un servidor web de *Flask* que utiliza la librería *Flask Assistant*. Sin embargo, para que podamos realizar llamadas a nuestro servidor web, será necesario que este se encuentre en una dirección pública. Mientras nos encontremos en estado de prueba, podemos hacer uso de algún servicio de *tunneling* como *Ngrok*, para exponer nuestro aplicativo a la web. En este caso en particular, utilizaremos *Heroku* que ofrece la opción de guardar nuestro aplicativo en la nube, con una dirección pública a la cual nuestro *webhook* de *Dialogflow* puede acceder para hacer las llamadas correspondientes.
Nuestro script **app.py** hasta este punto es el siguiente:
```python
from flask import Flask
from flask_assistant import Assistant, tell
from flask_cors import CORS
import GetSnap

app = Flask(__name__)

app.config['ASSIST_ACTIONS_ON_GOOGLE'] = True
app.config['INTEGRATIONS'] = ['ACTIONS_ON_GOOGLE']

cors = CORS(app)
assist = Assistant(app, route='/google')


@app.route("/", methods=['GET'])
def main():
    return "Eureka"

@assist.action('tv-watch')
def google_tv_watch():
    speech,url = GetSnap.return_speech()
    return tell("I see " + speech[:415]).card(
        text="See...",
        title="Image:",
        img_url=url
    )

if __name__ == '__main__':
    app.run(threaded=True, port=5000)
```
## Debemos subir nuestro proyecto a Heroku
Nuestro *web server* actualmente corre desde nuestro *Local Host*. Esto para probar que nuestro código funciona, está muy bien. Sin embargo, para que podamos activarlo mediante el *Google Assistant*, será necesario que se encuentre expuesto desde una dirección pública. Aquí será muy útil el uso de *Heroku*, una plataforma basada en nube que soporta diversos lenguajes de programación y se utiliza mediante *Git*.
En primer lugar, nos dirijmos a [Heroku](https://www.heroku.com/), y nos registramos si no contamos con una cuenta.
![Heroku Landing](https://i.ibb.co/5szqf5S/HK-SU-1.png)
Ingresamos nuestra información... Luego damos click en crear cuenta.
![Heroku SignUp](https://i.ibb.co/K0KVy3t/HK-SU-2.png)
Posteriormente, es necesario validar nuestra cuenta desde nuestro correo.
![ConfirmHerkouAccount](https://i.ibb.co/vZrHp5C/HK-SU-3.png)
Y finalmente, crear una contraseña.
![CreatePasswordHerokuAccount](https://i.ibb.co/SrXyFrb/HK-SU-4.png)
*Heroku* funciona a través de la línea de comandos *Heroku CLI*, es por esto que es importante haber instalado el ***Git Bash*** pues es ahí donde correremos los comandos.
Debemos ingresar a [*Heroku Set up*](https://devcenter.heroku.com/articles/getting-started-with-python#set-up) y elegir la descarga apropiada para nuestra plataforma (Windows, macOS, o Ubuntu). Habiendo instalado el *Heroku CLI*, ingresamos el comando `heroku login` y aparece un prompt en el que ingresamos cualquier tecla (excepto "q" que saldrá) para ser redireccionados al navegador ([Heroku Login](https://cli-auth.heroku.com/auth/browser/)) en el que debemos autenticarnos con las credenciales previamente generadas. Es necesario este paso para que funcionen correctamente los comandos `heroku`y `git`.
Habiendo instalado y configurado apropiadamente el *Heroku CLI*, debemos crear nuestro repositorio de *GitHub* y vincularlo con nuestro directorio local. 
En primer lugar creamos nuestro repositorio desde [GitHub](https://github.com/).
![GitHubRepoCreate](https://i.ibb.co/MCNbBjp/GH-R-1.png)
Le damos un nombre al repositorio, y lo creamos.
![GitHubRepoCreation](https://i.ibb.co/6tQbTzP/GH-R-2.png)
Luego accedemos a nuestro directorio local desde el *Git Bash*, y ejecutamos los comandos para subir nuestro proyecto.

 1. Inicializar el directorio local como un repositorio de Git
```git
$ git init
```
 2. Agregar los archivos de nuestro nuevo repositorio local. Esto lo añadimos al área de ensayo, para el primer *commit*.
```git
$ git add .
```
 3. Realizamos el commit de los archivos que hemos añadido al área de ensayo en nuestro repositorio local.
```git
$ git commit -m "Primer commit"
```
 4. En la sección superior de la página de GitHub que acabamos de crear aparecerá la URL del repositorio remoto.
 ![GitHubRepoLink](https://ibb.co/D45pkBZ)
 5. En la línea de comando, agregamos el URL para el repositorio remoto, desde nuestro repositorio local.
```git
$ git remote add origin <URL repositorio remoto>
# Este comando configura el nuevo URL remoto
$ git remote -v
# Este comando verifica el nuevo URL remoto
```
 6. Finalmente, publicamos nuestro proyecto al repositorio de GitHub.
```git
$ git push origin master
```
Ahora finalmente pasamos a desplegar nuestro aplicativo en Heroku, debemos ejecutar los siguientes comandos:
```git
$ heroku create
# Este comando crea el app
$ git push heroku master
# Este comando despliega nuestro proyecto al app que hemos creado
$ heroku ps:scale web=1
# Este comando asegura que al menos una instancia del aplicativo esté corriendo
$ heroku open
# Si todo ha salido bien hasta este punto, deberíamos ver una página que dice "Eureka"
$ heroku logs --tail
# Este comando nos permitirá ver los logs y hacer debugging y troubleshooting luego de desplegar la app.
```
Al ejecutar el comando `heroku create`, creamos el app y obtendremos en consola la dirección pública de nuestro aplicativo. Esta dirección es muy importante, debemos guardarla para utilizarla en la siguiente etapa.
![Heroku App Link](https://i.ibb.co/LpTvHx6/HK-SU-5.png)
**La dirección que le debe aparecer es distinta, la que aparece en su consola es la que debe guardar.**

## Conectar con Dialogflow

Una vez que hemos subido nuestro código a Heroku, ya tenemos una dirección pública a la cual podemos referirnos mediante un webhook.
Para empezar nos dirigimos a [Dialogflow](https://dialogflow.com/) y utilizamos nuestra cuenta de **Google** para registrarse.
![Dialogflow Sign In](https://i.ibb.co/1QWd2Fk/DF-SI-1.png)
La plataforma nos permite hacer esto de forma automática si tenemos nuestra cuenta activa en el navegador. Debemos concederle permiso a Dialogflow, y de esta forma accedemos a la página principal.
![Dialogflow SignIn](https://i.ibb.co/K75mxYF/DF-SI-2.png)
Luego de ingresar con nuestra cuenta, nos dirigimos a la consola. 
![DialogflowLanding](https://i.ibb.co/FsKCwQw/DF-SI-3.png)
Seremos redirigidos a la página de inicio. Aquí debemos especificar nuestro país y acceder a los términos y condiciones. En primer lugar será necesario crear un nuevo agente, y darle un nombre como "WhatDoYouSee" para identificarlo. Luego especificamos el idioma por defecto, y se creará un proyecto de *Google* de forma automática al guardar. Para este proyecto, usaremos el idioma inglés pues la respuesta del reconocimiento de la imagen estará en inglés, y deseamos mantener la concordancia. Damos "*click*" en el botón azul que dice "*Create*" para crear el agente.
![DialogflowCreateAgent](https://i.ibb.co/RjjPHfq/DF-TI-2.png)
Luego debemos crear un nuevo *intent*, es decir intención o propósito. Este será el que mapeamos a la función *tell* mediante el decorador *action* en la ruta de nuestro *web server* de *Flask*. Le damos el nombre "*tv-watch*". Esto lo haremos mediante el botón azul que dice "*Create Intent*" o en la barra lateral, ubicando la sección de *Intents*, dando "*click*" en el símbolo de suma "+".
![Dialogflow Create Intent](https://i.ibb.co/PWnhbVx/DF-TI-1.png)
Luego de crear nuestro *intent* y especificar su nombre, debemos indicar las frases con las que se ha de entrenar al asistente para reconocer nuestra intención.
Debido a que el software de reconocimiento de imágenes *Imagga* nos devuelve la clasificación en palabras en inglés, tiene sentido utilizar frases de entrenamiento en inglés. Usaremos frases de entrenamiento como "what is in sight", "what is it", "what is in view", o "what do you see", ya que esto significa "¿qué ves?", y es precisamente lo que hará el software, decirnos qué ve. No olvidemos guardar los cambios realizados mediante el botón azul que dice "*Save*".
![Dialogflow Intent Training Phrases](https://i.ibb.co/NLtrG97/DF-TI-3.png)
En la misma página, deslizamos hacia abajo, y damos click a activar la opción de *Fulfillment*.
![DialogFlow Intent Fulfillment](https://i.ibb.co/r5WJNvx/DF-TI-4.png) 
Luego de esto, habilitamos la opción de llamada de *webhook* para nuestro *intent*.
![DialogFlow Intent Fulfillment with Webhook](https://i.ibb.co/cLCWPB2/DF-TI-5.png)
Luego de haber habilitado esta opción, nos dirigimos en la barra lateral izquierda a la sección de *Fulfillment*. Aquí, habilitaremos los webhooks para nuestro agente.
![DialogFlow Fulfillment](https://i.ibb.co/vc8msyq/DF-TI-6.png)
Para el siguiente paso, será importante tener a la mano la dirección pública de nuestra *app*, que obtuvimos luego de realizar el `heroku create`.  En el espacio especificado para la URL, introducimos la dirección de nuestro aplicativo de *Heroku*.
![DialogFlow Fulfillment Webhok](https://i.ibb.co/HBMHWcp/DF-TI-7.png)
Para el último paso, necesitaremos nuestros *API Keys*. Para esto nos dirigimos a la configuración de nuestro agente, dando "*click*" en la ruedita o tuerca en la barra lateral, y deslizamos hacia abajo para encontrar nuestros *API Keys*. Es muy importante que copiemos el *Client Access Token*, y no el otro *API Key*.
![DialogFlow Settings APIKeys](https://i.ibb.co/2tJbN1M/DF-TI-8.png)
Finalmente, el último paso será dirigirnos al directorio donde está nuestro proyecto y repositorio local, desde el *Git Bash*. En nuestra línea de comando, introducimos la siguiente directiva:
```git
export CLIENT_ACCESS_TOKEN='CLIENT_ACCESS_TOKEN'
```
Donde `'CLIENT_ACCESS_TOKEN'` es el *API Key* llamado *Client access token* mostrado en la figura anterior. Luego de hacer esto, volvemos a seguir los pasos para actualizar nuestro repositorio de *Heroku*.
Agregar los archivos de nuestro nuevo repositorio local. Esto lo añadimos al área de ensayo, para el primer *commit*.
```git
$ git add .
```
Realizamos el commit de los archivos que hemos añadido al área de ensayo en nuestro repositorio local.
```git
$ git commit -m "Primer commit"
```
Publicamos nuestro proyecto al repositorio de GitHub.
```git
$ git push origin master
```
Y luego al *Heroku*.
```git
$ git push heroku master
```
``` git
$ heroku ps:scale web=1
``` 
Este comando asegura que al menos una instancia del aplicativo esté corriendo
```git
$ heroku logs --tail
```
Este comando nos permitirá ver los logs y hacer debugging y troubleshooting luego de desplegar la app.

Finalmente, para probar nuestra aplicación, entramos a la consola de *test*.
![DialogFlowIntegrations](https://i.ibb.co/Q88Qbxk/DF-TI-9.png)
![](https://i.ibb.co/1qkrg2Z/DF-TI-10.png)

Aquí hacemos click en *Talk to my test app* y escribimos nuestro intent "*what do you see*" o podemos utilizar el micrófono para decirlo.
![Test Console](https://i.ibb.co/nzvnQxB/DF-TI-11.png)

[↑](#toc)
