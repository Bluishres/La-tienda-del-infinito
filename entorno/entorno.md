# Entorno de Trabajo

- **Lenguajes**: Java, Dart.

- **Entornos de Desarrollo**: 

  - Backend: [IntelliJ](https://www.jetbrains.com/es-es/idea/download/#section=windows).
  - Frontend: [Android Studio 4.1.3](https://developer.android.com/studio).
  
- **SDK**: 

  - Backend: [Java SE Development Kit 8](https://www.oracle.com/es/java/technologies/javase/javase-jdk8-downloads.html).
  - Frontend: [Dart SDK 2.0.4](https://dart.dev/get-dart), [Android SDK](https://developer.android.com/studio), [Flutter](https://flutter.dev/docs/get-started/install/windows).
  
- **Control de versiones**: En este proyecto se usará GitHub como sistema de control de versiones. Estará distribuido a través de 3 repositorios, que son:
  1. **Repositorio principal**: Este repositorio tendrá 2 ramas, en la principal estarán los enlaces a los otros 2 repositorios, y en otra rama contendrá toda la documentación sobre el proyecto.
  2. **Repositorio de Frontend**: En este repositorio estará alojado el proyecto de Frontend.
  3. **Repositorio de Backend**: En este repositorio estará alojado el proyecto de Backend.
  
- **Arquitectura**: Se usará la Arquitectura Limpia por capas en ambos proyectos. ([Clean Architecture](https://www.genbeta.com/desarrollo/principios-de-una-arquitectura-limpia-mantenible-y-testeable)).

- **Maven**: Nos ayudará para gestionar todas las dependencias necesarias.

  <br>

## Índice de contenido

**[1. Instalación y configuración del entorno para el Frontend](#FRONTEND)**

**[&nbsp;&nbsp;&nbsp; - Instalación de Android Studio](#ANDROID)**

**[&nbsp;&nbsp;&nbsp; - Instalación de Dart SDK](#DART)**

**[&nbsp;&nbsp;&nbsp; - Instalación de Flutter](#FLUTTER)**

**[&nbsp;&nbsp;&nbsp; - Configuración de Android Studio](#CONFANDROID)**

**[2. Instalación y configuración del entorno para el Backend](#BACKEND)**

**[&nbsp;&nbsp;&nbsp; - Instalación de Java 8 SDK](#JAVA)**

**[&nbsp;&nbsp;&nbsp; - Instalación de IntelliJ](#INTELLIJ)**

  <br>
  <a name="FRONTEND"></a>

## Instalación y configuración del entorno para el Frontend

Esta explicación está hecha en Windows 10 como sistema operativo.

<a name="ANDROID"></a>

### Instalación de Android Studio

Para la instalación del entorno de desarrollo del Frontend, necesitaremos instalar [Android Studio](https://developer.android.com/studio) el cual contendrá también el SDK de Android. Tenéis los enlaces al principio de este apartado.

<p align="center"><img src=".\resources\android1.PNG" style="width:50%; height:50%;" /></p>

<br>

<p align="center"><img src=".\resources\Android2.PNG" style="width:60%; height:60%;" /></p>

<br>

<p align="center"><img src=".\resources\Android3.PNG" style="width:50%; height:50%;" /></p>

<br>

<p align="center"><img src=".\resources\Android4.PNG" style="width:50%; height:50%;" /></p>

<br>

<p align="center"><img src=".\resources\Android6.PNG" style="width:50%; height:50%;" /></p>

<br>
<a name="DART"></a>

### Instalación de Dart SDK

Para la instalación de Dart SDK, primero debemos descargar e instalar Chocolatey. Accederemos a la terminal de Windows como administrador e insertaremos este comando:

```
@powershell -NoProfile -ExecutionPolicy unrestricted -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%chocolateybin
```

Una vez termine, reiniciaremos el ordenador para que se termine de instalar.

Una vez lo tengamos, para instalar Dart SDK bastará con poner en la terminal lo siguiente:

```
choco install dart-sdk
```

<p align="center"><img src=".\resources\DART.PNG" style="width:50%; height:50%;" /></p>

<br>
<a name="FLUTTER"></a>

### Instalación de Flutter

Descargaremos Flutter SDK desde este [enlace](https://flutter.dev/docs/get-started/install/windows).

<p align="center"><img src=".\resources\Flutter.PNG" style="width:50%; height:50%;" /></p>

Una vez descargado, descomprimimos el zip en esta ruta (puede ser cualquier otra mientras no tenga que tener privilegios de administrador para acceder): C:\src\flutter\ **Aqui_el_contenido_del_zip_dentro_de_la_carpeta_flutter**

Ahora configuraremos las variables de entorno para añadir Flutter.

En primer lugar pondremos 'env' en el buscador y le daremos a *Editar las variables de entorno del sistema*: 

<p align="center"><img src=".\resources\Flutter2.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\Flutter3.PNG" style="width:50%; height:50%;" /></p>

Entraremos en *Variables de entorno...* y le daremos en las variables del usuario a editar seleccionando antes *path*

<p align="center"><img src=".\resources\Flutter4.PNG" style="width:50%; height:50%;" /></p>

En la pantalla que se nos abre haremos clic en nuevo y añadiremos lo siguiente:

<p align="center"><img src=".\resources\Flutter5.PNG" style="width:50%; height:50%;" /></p>

Una vez hecho esto, reiniciamos el terminal si lo teníamos abierto en modo administrador, iremos al directorio donde instalamos flutter y ejecutaremos `flutter doctor` para comprobar que se ha instalado correctamente:

<p align="center"><img src=".\resources\Flutter6.PNG" style="width:50%; height:50%;" /></p>



#### Posible error

Si saliera en amarillo Android toolchain al ejecutar `flutter doctor`, ejecutar `flutter doctor --android-licenses` y luego volver a ejecutar `flutter doctor` para asegurarnos que está todo instalado correctamente.

<br>
<a name="CONFANDROID"></a>

### Configuración de Android Studio

Una vez realizado los pasos previos, abriremos Android Studio y pasaremos a configurar el emulador que usaremos para probar la aplicación.

En primer lugar, tendréis que activar la virtualización en la bios si no lo teníais ya activada, ya que si no, no funcionará el emulador. En la mayoría de casos suele estar activada por defecto por lo que solo hacerlo en caso de que no os funcione el emulador después de seguir los pasos a continuación.

Una vez iniciado Android Studio, crearemos un nuevo proyecto vacío o abriremos uno que tengamos ya creado para instalar y configurar Dart y Flutter. En este caso crearemos uno nuevo para los que no lo hayan usado nunca:

<p align="center"><img src=".\resources\confAndroid.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\confAndroid2.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\confAndroid3.PNG" style="width:50%; height:50%;" /></p>

Una vez dentro del entorno, iremos al AVD Manager para crear un nuevo dispositivo virtual y seguiremos los pasos a continuación:

<p align="center"><img src=".\resources\AVDAndroid.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\AVDAndroid2.PNG" style="width:50%; height:50%;" /></p>

En este paso, podremos elegir el teléfono que queramos, yo elegí uno con 5,0 pulgadas:

<p align="center"><img src=".\resources\AVDAndroid3.PNG" style="width:50%; height:50%;" /></p>

Y para la versión de Android, elegiremos la 11 para testear la app:

<p align="center"><img src=".\resources\AVDAndroid4.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\AVDAndroid5.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\AVDAndroid6.PNG" style="width:50%; height:50%;" /></p>

Para probar que todo ha ido bien y funciona, lo podemos ejecutar dándole clic a play:

<p align="center"><img src=".\resources\AVDAndroid7.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\AVDAndroid8.PNG" style="width:50%; height:50%;" /></p>

Ya tenemos configurado nuestro emulador.<br>A continuación, iremos a *file/settings/plugin* y buscaremos en el Marketplace *Dart* y *Flutter* y los instalaremos:

<p align="center"><img src=".\resources\confAndroid4.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\confAndroid5.PNG" style="width:50%; height:50%;" /></p>

Y reiniciaremos una vez instalados dándole clic en Restart IDE para que se terminen de instalar:

<p align="center"><img src=".\resources\confAndroid6.PNG" style="width:50%; height:50%;" /></p>

Ya tendremos el entorno listo para la importación del proyecto.

<br>
<a name="BACKEND"></a>

## Instalación y configuración del entorno para el Backend

Esta explicación está hecha en Windows 10 como sistema operativo.

<a name="JAVA"></a>

### Instalación de Java 8 SDK

Descargaremos [Java 8 SDK](https://www.oracle.com/es/java/technologies/javase/javase-jdk8-downloads.html) desde el siguiente [enlace](https://drive.google.com/file/d/1MxkOd2XeNbZZ-u5yeNbjvSY6PTQw95WE/view?usp=sharing) y lo instalaremos.

<p align="center"><img src=".\resources\Java.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\Java2.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\Java3.PNG" style="width:50%; height:50%;" /></p>

<p align="center"><img src=".\resources\Java4.PNG" style="width:50%; height:50%;" /></p>

<br>
<a name="INTELLIJ"></a>

### Instalación de IntelliJ

En nuestro caso, hemos usado IntelliJ Ultimate, pero también valdría la versión gratuita Community.

Simplemente descargar e instalar desde la [página web oficial](https://www.jetbrains.com/es-es/idea/download/#section=windows).

Una vez instalado, importaremos el proyecto.