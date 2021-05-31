# Tecnologías de desarrollo.

## Índice de contenido

**[1. Introducción.](#INTRO)**

**[2. Tecnologías.](#TECNOLOGIAS)**

<br>
<a name="INTRO"></a>

## Introducción

En este apartado de **Tecnologías de desarrollo** expondremos las diferentes tecnologías y herramientas usadas en nuestro proyecto.

Tanto a nivel de Back y Front como externo, por ejemplo el Prototipado realizado con **Adobe XD**.

<br>
<a name="TECNOLOGIAS"></a>

## Tecnologías

- **Flutter**

  Flutter es un framework que tiene la capacidad de desarrollar aplicaciones multiplataforma. Fue creado por Google y publicado como proyecto de código abierto a finales de 2018.

  La versión inicial constaba de un gran número de bibliotecas para interfaces como Android e IOS. Nosotros nos hemos basado en la última versión que es Flutter 2.

  

  La ventaja principal de dessarrollar una aplicación con Flutter es que conservando una interfaz de lo más normal y con un solo código, podrás ejecutarlo en diferentes plataformas.

  Aunque sea una tecnología joven, muchas empresas están empezando a ver su potencial y por ello están empezando a desarrollar proyectos con esta tecnología.

  Google por ejemplo, usa Flutter para sus distintos módulos como Google Assistant o la interfaz de usuario de Google Home Hub.

  

  Por último, decir que esta tecnología usa el lenguaje Dart. Un lenguaje nuevo y personalizado para Flutter, pero muy visual y directo al programar con él.

  <br>

- **Spring**

  Spring como Spring Core es un framework usado para Java con el que podemos crear código de alto rendimiento, elegante y reutilizable gracias a las tecnologías que trae.

  

  Algunas de las tecnologías y ventajas que trae son: 

  1. **Inyección de dependencias**, Eventos, conversiones...
  2. **Acceso a datos**: DAO, JDBC, ORM...
  3. **Testing**: Objetos Mock, Spring MVC...
  4. **MVC** (Modelo - Vista - Controlador).
  5. **Seguridad** (Spring Security).
  6. **Implementación POJO** (Plain Old Java Object).

  

  La **Inyección de Depencias** (Dependency Injection) es de lo más importante que trae Spring Core porque hace que la aplicación pase a estar modularizada y por lo tanto, muy independiente. Esto hace que sea fácil de reutilizar y en la fase de testeo fácil de probar cada parte sin tener que implicar a las otras.

  

  Spring es como el framework base de Java ya que da soporte a varios frameworks como: **Hibernate**, JSF, EJB...

  <br>

- **Spring Boot**

  Spring Boot es una tecnología que se encuentra dentro del propio Spring Core.

  Una de las cosas por la que existe Spring Boot es que Spring tal cual tenía una configuración inicial muy pesada. 

  

  Por lo tanto, tenemos dos grandes novedades con respecto al Core, éstas son:

  

  1. **Contenedor de aplicaciones integrado (Archivos .jar)**

     Estos archivos tienen la función de bajo un solo archivo poder ejecutar toda una gran aplicación. Todas las configuraciones, preparaciones viene incluído en este archivo. Por lo que nos ahorra tener que configurar todo siempre desde 0.

     Esto lo hace integrando el servidor de aplicaciones en este archivo .jar y se ejecuta cuando arrancamos la app.

     Al realizarse de esta forma da pie a crear aplicaciones con arquitecturas de microservicio, ya que su distribución puede ser a través de imágenes Docker.

     <br>

  2. **Dependencias Starters - Initializers**

     Spring Boot trae unas dependencias llamadas starters, que podemos añadir a nuestro proyecto con gran facilidad. Algunos ejemplos pueden ser: Controlador REST, accesos a bases de datos usando JDBC...

     Con el starter podemos quedarnos tranquilo de que no se nos olvida nada ya que agrupa todas las dependencias que hayamos escogido.

     Existe una página desde la que se nos hace aún más fácil este procedimiento.

     Nos crea un proyecto del que podemos empezar de 0 o extraer de su archivo POM las dependencias que queramos.

     En el siguiente enlace se encuentra la página comentada:

     [Spring Initializr](https://start.spring.io/)

     <br>

- **Docker**

  Docker es una plataforma de software que le permite crear, probar e implementar aplicaciones rápidamente. Docker empaqueta software en unidades estandarizadas llamadas contenedores que incluyen todo lo necesario para que el software se ejecute, incluidas bibliotecas, herramientas de sistema, código y tiempo de ejecución. Con Docker, puede implementar y ajustar la escala de aplicaciones rápidamente en cualquier entorno con la certeza de saber que su código se ejecutará.

  La ejecución de Docker en [AWS](https://aws.amazon.com/es/) (**Amazon Web Service**) les ofrece a desarrolladores y administradores una manera muy confiable y económica de crear, enviar y ejecutar aplicaciones distribuidas en cualquier escala.

  Gracias a la unión de Docker y AWS los desarrolladores pueden acelerar la creación y entrega de sus aplicaciones.

  Docker es como una especie de máquina virtual en la que ejecutamos nuestros contenedores.

  En nuestro caso, hemos dockerizado nuestra Base de Datos MySQL a través de Docker Compose. Esto lo hemos puesto en funcionamiento en una instancia de AWS junto con la aplicación Backend.

<br>