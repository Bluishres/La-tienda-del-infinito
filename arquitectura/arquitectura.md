# Arquitectura de la aplicación.

## Índice de contenido

**[1. Introducción.](#INTRO)**

**[2. Arquitectura Limpia.](#ARQUITECTURA_LIMPIA)**

**[3. Modelo MVC](#MODELO_MVC)**

<br>
<a name="INTRO"></a>

## Introducción

En este apartado de **Arquitectura** explicamos la estructura principal del proyecto y como está conformado.

Se habla sobre la **Arquitectura Limpia** usada en el Back ya que es una nueva arquitectura aprendida y que adapta las mismas ideas que la principalmente usada por nosotros **Modelo - Vista - Controlador (MVC)**.

<br>
<a name="ARQUITECTURA_LIMPIA"></a>

## Arquitectura Limpia

<img src=".\resources\back1.PNG" />

No existe una única arquitectura limpia, pero todas ellas se basan en el mismo principio de diseño de software: La separación de responsabilidades. Se establece una arquitectura por capas, cada una de ellas con una responsabilidad específica. Esta es la que hemos usado para el backend.

Una arquitectura limpia se caracteriza por:

- **Independencia de los frameworks**: Los frameworks deberían ser herramientas, y no obligarnos a actuar de una determinada manera debido a sus restricciones.
- **Aplicación testable**: Debemos poder probar nuestras reglas de negocio sin pensar en base de datos, interface gráfica u otros componentes no esenciales de nuestro sistema.
- **Independencia de la UI**: Si la UI cambia a menudo esto no puede afectar al resto de nuestro sistema, que tiene que ser independiente.
- **Independencia de la base de datos**: Deberíamos poder cambiar de Oracle, a SQL Server, a MongoDB, a Casandra o a cualquier otra base de datos sin que afectara demasiado a nuestro sistema.
- **Independencia de cualquier entidad externa**: No deberíamos saber nada de entidades externas, por lo que no deberemos depender de ellas.



A continuación, podéis ver un esquema de ejemplo sobre esta arquitectura:

<img src=".\resources\450_1000.jpg" />

<br>

Cada círculo representa un área del software:

- **Enterprise Business Rules o Entidades**: Área que encapsula la lógica de negocio a nivel empresarial. Aquí estarán los objetos, estructuras de datos y/o funciones que permiten modelar toda la lógica empresarial. *Entidades* del tipo Persona, Grupo, Pedido, Línea de Pedido, Factura, etc. formarán parte de esta capa.
- **Application Business Rules o Casos de uso**: Área que contiene las reglas de negocio específicas de la aplicación. Aquí se implementan los *casos de uso* que hace nuestra aplicación sobre las entidades empresariales. Mientras la capa anterior se ocupaba de los actores, ésta se ocupa de las interacciones (asociar una Persona como miembro de un Grupo, crear un Pedido con Líneas de Pedido…). Los cambios en esta capa no deberían afectar a las entidades, en cambio una modificación en las entidades si puede afectar a los casos de uso.
- **Interface Adapters o Adaptadores de Interfaz**: Área que contiene un conjunto de adaptadores donde se convierten datos entendibles por los casos de uso a datos aceptados por elementos externos, y viceversa. Con respecto al sistema de persistencia tendremos *Repositorios* que realicen esa adaptación en función del sistema de persistencia utilizado (ORMs, JPA, Hibernate, MyBatis…). Otro ejemplo serían los convertidores de servicios SOAP, o estructuras JSON, proporcionadas por algún servicio externo. Al igual que el anterior, esta capa no debería afectar a las entidades y a las reglas de negocio, en cambio una modificación en estas si puede afectar a los adaptadores.
- **Frameworks y Drivers**: Área más externa que se compone de frameworks y herramientas como la base de datos, el framework web, sistemas de testing, etc. Al igual que el anterior, esta capa no debería afectar a las capas anteriores, en cambio una modificación en estas si puede afectar a esta capa.

Con la Arquitectura Limpia, podremos asegurarnos el cumplimiento del principio S.O.L.I.D de la programación orientada a objetos:

- S – Single Responsibility Principle o Principio de Responsabilidad Única (SRP)

  ​	Según este principio una clase debería tener una, y solo una, razón para cambiar.

- O – Open/Closed Principle o Principio de Abierto/Cerrado (OCP)

  ​	Según este principio deberías ser capaz de extender el comportamiento de una clase, sin modificarla.

- L – Liskov Substitution Principle o Principio de Sustitución de Liskov (LSP)

  ​	Según este principio las clases derivadas deben poder sustituirse por sus clases base.

- I – Interface Segregation Principle o Principio de Segregación de la Interfaz (ISP)

  ​	Según este principio haz interfaces que sean específicas para un tipo de cliente.

- D – Dependency Inversion Principle o Principio de Inversión de Dependencias (DIP)

  ​	Según este principio depende de abstracciones, no de clases concretas.
  
  

<br>
<a name="MODELO_MVC"></a>

## Modelo MVC

<img src=".\resources\MVC FRONT.png" />

MVC es una propuesta de arquitectura del software utilizada para separar el código por sus distintas responsabilidades, manteniendo distintas capas que se encargan de hacer una tarea muy concreta, lo que ofrece beneficios diversos. Este es el modelo seguido en el frontend de nuestra aplicación.

Es usado inicialmente en sistemas donde se requiere el uso de interfaces de usuario, aunque en la práctica el mismo patrón de arquitectura se puede utilizar para distintos tipos de aplicaciones. Surge de la necesidad de crear software más robusto con un ciclo de vida más adecuado, donde se potencie la facilidad de mantenimiento, reutilización del código y la separación de conceptos.

Su fundamento es la separación del código en tres capas diferentes, acotadas por su responsabilidad, en lo que se llaman Modelos, Vistas y Controladores.

### Modelo

Es la capa donde se trabaja con los datos, por tanto contendrá mecanismos para acceder a la información y también para actualizar su estado. Los datos los tendremos habitualmente en una base de datos, por lo que en los modelos tendremos todas las funciones que accederán a las tablas y harán los correspondientes *selects, updates, inserts*, etc.

### Vista

Las vistas, como su nombre nos hace entender, contienen el código de nuestra aplicación que va a producir la visualización de las interfaces de usuario, o sea, el código que nos permitirá renderizar los estados de nuestra aplicación en HTML. En las vistas nada más tenemos los códigos HTML y PHP que nos permite mostrar la salida.

### Controlador

Contiene el código necesario para responder a las acciones que se solicitan en la aplicación. En realidad es una capa que sirve de enlace entre las vistas y los modelos, respondiendo a los mecanismos que puedan requerirse para implementar las necesidades de nuestra aplicación.



