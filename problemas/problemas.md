# Problemas durante el desarrollo.

## Índice de contenido

**[1. Introducción.](#INTRO)**

**[2. Problemas referentes al Back.](#PROB-BACK)**

**[3. Problemas referentes al Front.](#PROB-FRONT)**

<br>
<a name="INTRO"></a>

## Introducción

En este apartado de **Problemas** comentamos de forma general que problemas u obstáculos se nos han presentado a la hora de realizar el proyecto.

Aunque nuestro proyecto haya tenido una parte de investigación por la parte del Front con Flutter, en general nuestro proyecto es de desarrollo ya que hemos puesto en práctica muchas de las cosas aprendidas en el curso.

Debido a lo anterior, nos lleva a dividir este apartado en problemas en el Back y otro en el Front. Al ser dos partes muy diferenciadas con tecnologías muy diferentes nos lleva a realizarlo de esta forma.

<br>
<a name="PROB-BACK"></a>

## Problemas referentes al Back



<br>
<a name="PROB-FRONT"></a>

## Problemas referentes al Front

- **Diseño en Flutter** (Scaffold, Container...)

  Al ser una tecnología nueva y que se nos presentó hace relativamente poco, el diseño es una parte importante a comentar.

  Flutter da facilidad a la hora de diseñar ya que es todo muy visual gracias al Hot Reload (Carga Instántanea), pero como todo al principio lleva tiempo el comprender las estructuras necesarias para crear una pantalla.

  Gracias a esa facilidad de que todo sea muy visual y directo, este problema solo fue al principio de empezar con Flutter.

  Hablando de la estructura que tiene Flutter a la hora de dibujar sus vistas, es muy diferente a otras aprendidas en el curso. Por ejemplo, en JavaFX era totalmente diferente de Flutter y React ya que era todo a través de la propia lógica que tenía JavaFX.

  Por otra parte, está React que si es más parecido a Flutter. Esto se debe aparte de los estados de los que se habla abajo, también a la estructura que comparten. React tiene una estructura en la que el ***Render*** es el que dibuja la pantalla. Bajo un concepto parecido tenemos Flutter con su método ***Build*** que es el que construye todo el apartado visual.

  <br>

- **Lógica en Flutter**

  Siguiendo la misma idea anterior, Flutter tiene un lenguaje diferente (Dart). Esto hace que aunque tenga cosas parecidas con otros lenguajes también hayan estructuras y nuevas formas que hay que saber para seguir una buena práctica.

  Por lo que, una vez aprendidas las formas y en general, la lógica que sigue esta herramienta multiplataforma, todo es muy fácil de llevar acabo una vez tienes las ideas claras.

  Al llevar más tiempo trabajando con herramientas usadas en el Backend, la lógica en Flutter ha supuesto algunos problemas más concretos.

  Algunos de estos problemas son:

  1. **Inclusión de Firebase y Base de Datos local en Flutter al mismo tiempo**. Durante el curso, lo más cercano que hemos hecho a esto ha sido conectar solo un Backend con una Base de Datos local con un Frontend hecho en JavaFX. Por lo tanto, al principio este punto fue un reto ya que debíamos tener en cuenta la entrada y salida de datos por dos medios diferentes.
  2. **Estados en Flutter**. React también usa el concepto de estados, incluso de una forma más difícil de controlar. Aún habiendo usado durante el curso los estados de React, en Flutter el uso de éstos es diferente. Por lo que, en ciertas funcionalidades que necesitábamos usarlos al principio se necesitó de tiempo tanto para investigarlos como para afianzarlos en el propio código. Un ejemplo concreto fue al actualizar el estado del usuario si estaba logueado. En este caso, una vez el usuario inicia sesión en la aplicación, hacemos ***POP***, es decir, navegar a la anterior pantalla. Y esta misma pantalla debe actualizar su estado, sin embargo, a nosotros no se nos actualizaba el estado. Ya que no era la misma forma de uso que en React. Tuvimos que mirar al final la documentación oficial para informarnos sobre los métodos Stateful Widget.

<br>