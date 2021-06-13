ANEXOS.

## Índice de contenido

**[1. Introducción.](#INTRO)**

**[2. ANEXO I: Despliegue de la aplicación.](#DESPLIEGUE)**

**[&nbsp;&nbsp;&nbsp; - Backend](#BACK)**

**[&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Docker Hub](#DOCKER)**

**[&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Amazon Web Services](#AWS)**

**[&nbsp;&nbsp;&nbsp; - Frontend](#FRONT)**

**[&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Bitrise y Firebase](#BI-FIRE)**

**[3. ANEXO II: Manual de Usuario.](#MAN-USU)**

<br>
<a name="INTRO"></a>

## Introducción

En este apartado de **Anexos** podréis encontrar tanto el **Despliegue de la aplicación** como un **Manual de Usuario**.

En el anexo de Despliegue se explica como se ha desplegado y usado la integración continua para cada aplicación mediante varias plataformas usadas, entre ellas Firebase.

En el anexo de Manual de Usuario podéis ver un pequeño vídeo de como un usuario puede llegar a usar nuestra aplicación.

<br>
<a name="DESPLIEGUE"></a>

## ANEXO I: Despliegue de la aplicación

En este apartado se detalla como se ha desplegado las respectivas aplicaciones en la nube con integración continua. Como requisito previo, se deben tener los proyectos ya en GitHub con su respectivo repositorio.

<br>

<a name="BACK"></a>

### Backend

<img src=".\resources\Despliegue backend.png" />

En el backend hemos usado 2 servicios en la nube: 

- [*Docker Hub*](https://hub.docker.com/): es un servicio proporcionado por **Docker** para encontrar y compartir imágenes de contenedores en nuestros ordenadores. Este tiene 2 funcionalidades las cuales son las que usamos:
  - La asociación de un repositorio de GitHub al repositorio de Docker Hub.
  - La función de autobuild cuando detecte que en GitHub hay un nuevo commit en la rama de producción.
- [*Amazon Web Services EC2*](https://aws.amazon.com/): es un servicio web que proporciona capacidad informática en la nube segura y de tamaño modificable. Está diseñado para simplificar el uso de la informática en la nube a escala web para los desarrolladores. La sencilla interfaz de servicios web de Amazon EC2 permite obtener y configurar capacidad con una fricción mínima. Proporciona un control completo sobre los recursos informáticos y puede ejecutarse en el entorno informático acreditado de Amazon.

Para la utilización de este último hemos usado la capa de free tier, la cual es gratuita durante 1 año con cierta limitaciones.

<br>

<a name="DOCKER"></a>

#### Docker Hub

En primer lugar para realizar la integración continua en Docker Hub, se debe de crear un repositorio:

<img src="C:.\resources\docker0.PNG" style="zoom:38%;" />

<img src=".\resources\docker1.PNG" style="zoom:38%;" />

Una vez hecho esto, debemos irnos a nuestro proyecto y configurar nuestro Dockerfile que será el que le dirá que hacer a Docker Hub cuando realice el build.

<img src=".\resources\docker1-2.PNG" style="zoom:38%;" />

```dockerfile
#
# Build stage, o fase build, donde le diremos a docker que compile nuestra API con maven.
#
FROM maven:3.6.0-jdk-8-slim AS build
COPY src /home/latiendadelinfinito/src
COPY pom.xml /home/latiendadelinfinito
RUN mvn -f /home/latiendadelinfinito/pom.xml clean package -Dmaven.test.skip=true

#
# Package stage, o fase de empaquetamiento, donde moveremos el .jar generado previamente al contenedor de docker hub,
# y le diremos con "ENTRYPOINT" el comando a ejecutyar cuando el contenedor este activo.
#
FROM openjdk:8
COPY --from=build /home/latiendadelinfinito/target/*.jar /usr/local/TDI/app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/usr/local/TDI/app.jar"]
```

Una vez creado y subido a GitHub, el siguiente paso será ir al apartado de builds en Docker Hub y asociar nuestro Repositorio GitHub con el archivo DockerFile en la raíz y la siguiente configuración:

<img src=".\resources\docker2.PNG" style="zoom:38%;" />

<img src=".\resources\docker3.PNG" style="zoom:38%;" />

Una vez terminada la configuración, hacer clic en 'Save and Build' y Docker Hub compilará nuestra primera build en el tag latest del repositorio.

El repositorio está listo para recibir con escucha activa los commit del la rama de producción para hacer automáticamente build al contenedor.

<br>

<a name="AWS"></a>

#### Amazon Web Services EC2

Para comenzar, crear una cuenta para poder acceder a los servicios de [Amazon Web Services](https://aws.amazon.com/). En nuestro caso hemos usado Free Tier.

Una vez hecho eso, crearemos en el apartado de EC2 nuestra instancia, la única gratuita que podemos, con Ubuntu Server:

<img src=".\resources\aws.PNG" style="zoom:38%;" />

<img src=".\resources\aws2.PNG" style="zoom:38%;" />

<img src=".\resources\aws3.PNG" style="zoom:38%;" />

<img src=".\resources\aws4.PNG" style="zoom:38%;" />

* Debemos configurar los puertos 8080 y 3306 de MySQL en la instancia (o cualquier otro puerto que se vaya a utilizar) para que sea accesible.

<p align="center"><img src=".\resources\aws5.PNG" width="800" /></p>

* En este caso, podemos generar las claves en AWS, descargarlas (tendremos uno publico y privado), y usarlas para la conexión con la instancia por terminal.

Para conectarnos a nuestra instancia, podemos ir al apartado conectar una vez la tengamos en funcionamiento para la explicación de como podemos conectarnos a la terminal.

<img src=".\resources\aws6.PNG" style="zoom:38%;" />

<img src=".\resources\aws7.PNG" style="zoom:38%;" />

Para transferir archivos y conectados a la instancia, hemos usado [WinSCP](https://winscp.net/eng/download.php) que es un cliente SFTP, SCP, Amazon S3, WebDAV, y FTP, y [Putty](https://www.putty.org/) como complemento de este último.

Solamente introducir la ip o dns publicos, usuario 'ubuntu' y en 'Avanzado'/'Autentificación' examinar nuestra clave privada para que pueda conectarse:

<p align="center"><img src=".\resources\aws8.PNG" width="700" /></p>

<p align="center"><img src=".\resources\aws9.PNG" width="700" /></p>

Una vez listo, haremos clic en la consola de Putty e instalaremos Docker y Docker-compose, previamente haciendo `sudo apt update`:

<img src=".\resources\aws10.PNG" style="zoom:38%;" />

<p align="center"><img src=".\resources\aws11.PNG" width="700" /></p>

<p align="center"><img src=".\resources\aws12.PNG" width="700" /></p>

Terminada la instalación, hay que crear el Docker-compose.yml donde indicaremos que contenedores utilizará la instancia y subirlo a la instancia, este es el ejemplo de este proyecto:

```yaml
version: "3.3"
services:
  mysqldb:		# Contenedor mysql donde tendremos la base de datos de nuestra aplicación
    image: mysql:5.7
    container_name: Mysql5
    command:
      - --character-set-server=utf8
      - --collation-server=utf8_unicode_ci
      - --skip-character-set-client-handshake
      #- --lower_case_table_names=0
    restart: always
    environment:
      MYSQL_DATABASE: "tiendadinfinito"
      MYSQL_USER: "tdi"
      MYSQL_PASSWORD: "tdi"
      MYSQL_ROOT_PASSWORD: "root"

    ports:
      - 3311:3306
    expose:
      - 3306
    volumes:
      - ./res/db/mysql/db:/var/lib/mysql
  backendtdi:	#contenedor donde tenemos nuestro backend previamente configurado en docker-hub
    image: bluishres/latiendadelinfinitoback:latest 
    container_name: BackendInfinity
    # descomentar network_mode y extra_hosts si es para docker en ubuntu.
#    network_mode: host
#    extra_hosts:
#      - "host.docker.internal:127.0.0.1"
    restart: always
    expose:
      - 8080
    ports:
      - 8080:8080
```

<img src=".\resources\aws13.PNG" style="zoom:38%;" />

Hacemos `sudo docker compose up -d` en el directorio donde hayamos introducido el docker-compose.yml:

<img src=".\resources\aws14.PNG" style="zoom:38%;" />

Ya tendremos nuestra instancia lista con nuestro backend funcionando en la IP asignada por AWS.

En este punto, instalamos [cron/crontab](https://www.redeszone.net/2017/01/09/utilizar-cron-crontab-linux-programar-tareas/) y lo configuramos para que cada vez que la instancia se reinicie, ejecute los siguientes comandos para obtener la ultima actualización del backend: -`sudo docker pull bluishres/latiendadelinfinitoback` y `sudo docker-compose up -d` .

Como añadido, hemos configurado nuestra instancia con un DNS dinámico gratuito para que cada vez que se reinicie, obtenga la nueva ip. Esta configuración la hemos hecho mediante [noip](https://www.noip.com/) y esta guía de [Amazon Web Services](https://docs.aws.amazon.com/es_es/AWSEC2/latest/UserGuide/dynamic-dns.html).

<br>

<a name="FRONT"></a>

### Frontend

<img src=".\resources\Despliegue frontend.png" />

En el Frontend hemos usado 2 servicios en la nube:

- [Bitrise](https://www.bitrise.io/): es una plataforma de integración continua para automatizar el proceso de creación, prueba e implementación de aplicaciones. En nuestro caso, lo hemos configurado con GitHub para que, por cada commit en la rama de producción, se realice un build automaticamente y lo despliegue en Firebase AppDistribution a los testers deseados.
- [Firebase](https://firebase.google.com/?hl=es): es una plataforma en la nube para el desarrollo de aplicaciones web y móvil. Está disponible para distintas plataformas (iOS, Android y web), con lo que es más rápido trabajar en el desarrollo. En este caso, hemos usado tanto la autenticación, como el servicio de Storage para almacenar fotos de Firebase. Y para el despliegue su servicio App Distribution.

<br>

<a name="BI-FIRE"></a>

#### Bitrise y Firebase

En primer lugar, crear cuenta en [Bitrise](https://www.bitrise.io/), este ofrece un servicio gratuito de 14 días para ello.

Una vez creado la cuenta, crearemos una nueva app en la página, configuraremos a nuestro gusto y vincularemos GitHub:

<img src=".\resources\bitrise.PNG" style="zoom:38%;" />

<img src=".\resources\bitrise2.PNG" style="zoom:38%;" />

<img src=".\resources\bitrise3.PNG" style="zoom:38%;" />

Aquí colocaremos la rama por defecto del proyecto.

<img src=".\resources\bitrise4.PNG" style="zoom:38%;" />

<img src=".\resources\bitrise5.PNG" style="zoom:38%;" />

Aquí elegiremos nuestro proyecto:

<img src=".\resources\bitrise6.PNG" style="zoom:38%;" />

Y especificaremos las configuraciones oportunas:

<img src=".\resources\bitrise7.PNG" style="zoom:38%;" />

En este caso elegiremos el logo de nuestra aplicación si deseamos alguno:

<img src=".\resources\bitrise8.PNG" style="zoom:38%;" />

En este paso, seleccionar lo siguiente para que Bitrise configure los Webhook automaticamente:

<img src=".\resources\bitrise9.PNG" style="zoom:38%;" />

Una vez terminado, empezará a compilar la aplicación, pero aun no lo hemos asociado a Firebase, por lo que compilará nada más.

<img src=".\resources\bitrise10.PNG" style="zoom:38%;" />

En este punto, necesitaremos un proyecto en Firebase creado y configurado en nuestra aplicación (en la propia plataforma explican como hacerlo).

<img src=".\resources\bitrise11.PNG" style="zoom:38%;" />

Una vez creado el proyecto y teniendo la App Distribution funcionando en Firebase, debemos irnos al apartado de Workflow en Bitrise dentro de nuestra aplicación:

<img src=".\resources\bitrise22.PNG" style="zoom:38%;" />

Iremos al apartado de Triggers y seleccionaremos la rama o ramas que queremos que escuche Bitrise para el autobuild:

<img src=".\resources\bitrise12.PNG" style="zoom:38%;" />

<img src=".\resources\bitrise13.PNG" style="zoom:38%;" />

<img src=".\resources\bitrise14.PNG" style="zoom:38%;" />

Terminado esto, iremos al apartado de Workflows y añadiremos Flutter build después de Flutter Analyze y Firebase App Distribution al final para la distribucion a nuestros testers. A continuación podéis ver los proceso que realiza Bitrise:

<p align="center"><img src=".\resources\bitrise15.PNG" width="300" /></p>

<p align="center"><img src=".\resources\bitrise23.PNG" width="300" /></p>

Ahora configuraremos el apartado de Firebase para que pueda acceder a nuestra cuenta.

El primer apartado requerido es el Token que se puede obtener instalando firebase en el terminal y ejecutando `firebase login:ci`:

<img src=".\resources\bitrise16.PNG" style="zoom:38%;" />

Lo siguiente será el directorio del apk en Bitrise, poniendo la siguiente variable dejaremos el valor por defecto:

<img src=".\resources\bitrise17.PNG" style="zoom:38%;" />

A continuación, introducir el ID de nuestra APP:

<img src=".\resources\bitrise18.PNG" style="zoom:38%;" />

Aquí introducimos los testers que queramos que prueben nuestra aplicación:

<img src=".\resources\bitrise19.PNG" style="zoom:38%;" />

Esta será la nota junto con la version del release que queremos que tenga:

<img src=".\resources\bitrise20.PNG" style="zoom:38%;" />

Por ultimo, seleccionar true en este paso para mejorar las herramientas de Firebase:

<img src=".\resources\bitrise21.PNG" style="zoom:38%;" />



Una vez configurado todo, ya tendremos nuestra aplicación lista. Con el siguiente commit hacia la rama de producción se generará un build automáticamente y se enviará mediante Firebase a los testers para su correcta prueba.

<br>
<a name="MAN-USU"></a>

## ANEXO II: Manual de Usuario



<br>
