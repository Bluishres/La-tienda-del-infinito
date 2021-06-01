# Pruebas.

## Índice de contenido

**[1. Introducción.](#INTRO)**

**[2. Pruebas unitarias.](#PRUEBASUNITARIAS)**

**[&nbsp;&nbsp;&nbsp; - Pruebas de infraestructura.](#PRUEBASINFRA)**

**[4. Pruebas de integración.](#PRUEBASINTEGRA)**

**[5. Pruebas End-to-End.](#PRUEBASEND)**

<br>
<a name="INTRO"></a>

## Introducción

En este apartado de **Pruebas** se mostrarán todos los tests a nivel de Backend. Se podrá comprobar como dentro de la Arquitectura Limpia cada nivel tiene su tipo de Test.

Por lo que, se probará que cada funcionalidad funciona correctamente a través de estas pruebas.

<br>
<a name="PRUEBASUNITARIAS"></a>

## Pruebas unitarias

Las pruebas unitarias consisten en aislar una parte del código y comprobar que funciona a la perfección. Son las mejores prácticas a la hora de realizar test, ya que con ellas se detectan antes errores que, sin las pruebas unitarias, no se podrían detectar hasta fases más avanzadas como las pruebas de integración e incluso en la beta.

Para llevar a cabo buenas pruebas unitarias, deben estar estructuradas siguiendo las tres A’s del Unit Testing. Se trata de un concepto fundamental respecto a este tipo de pruebas, que describe un proceso compuesto de tres pasos: Arrange, Act y Assert. Más adelante los explicaremos mejor.

Antes de continuar, debemos recalcar unas recomendaciones a la hora de hacer tests:

- Las pruebas unitarias tienen que ser independientes. Si se produce cualquier tipo de mejora o cambio en los requerimientos, las pruebas unitarias no deberían verse afectados.
- Sigue una estructura clara y limpia. Escribe también los nombres identificativos de cada clase y de cada test.
- Corrige los bugs identificados durante las pruebas antes de continuar con el siguiente test.
- Realizar pruebas regularmente mientras programas, ya que cuanto más código escribas sin testear, más tendrás que revisar después y tardarás más a largo plazo.

<br>
<a name="PRUEBASINFRA"></a>

### Pruebas de infraestructura

Como su nombre indica, estos tests prueban la infraestructura del sistema, persistiendo nuestras entidades en la base de datos.

Explicaremos un ejemplo de este proyecto por partes:

<img src=".\resources\1.PNG" />

La etiqueta @RunWith indica que queremos ejecutar esos test con Spring.

La etiqueta @ContextConfiguration configura el contexto, donde está el fichero de configuración con todos los beans y las clases que queremos inyectar de forma automática, además en este mismo fichero especificamos que base de datos usar de nuestro fichero persistence.xml.

En estos tests inyectamos un EntityManager que usaremos para persistir. Para ello usamos la etiqueta @PersistenceContext, que anota un contexto de persistencia.

<img src=".\resources\2.PNG" />

Este es un ejemplo de test, que se traduciría como "debería crear nuevo usuario".

Las etiquetas usadas son:

- @Test que se coloca siempre encima del método test para que la aplicación lo reconozca como tal y se ejecute.

- @Transactional que obligar a que el EntityManager se ejecute dentro de un entorno transaccional. Si no lo hiciera, al ejecutar el método save() daría un error, ya que no existe una transacción activa.

Para los test siempre se diferencian 3 partes:

- Arrange o Organización: realiza la configuración y la inicialización necesarias para la prueba.
- Act o Actuación: tomar las medidas necesarias para la prueba.
- Assert o Afirmación: Verifica el (los) resultado(s) de la prueba. En el caso de la imagen, comprueba que el usuario creado anteriormente es el mismo que el persistido en la base de datos.

<br>

<br>
<a name="PRUEBASINTEGRA"></a>

## Pruebas de integración

Los test de integración comprueban la correcta unión entre las distintas capas, en el inyectamos el repositorio y el service de la entidad.

<img src=".\resources\3.PNG" />

En este caso los test prueban los casos de uso introducidos en el Service.

<img src=".\resources\4.PNG" />

En el ejemplo de arriba, el test comprueba el funcionamiento de nuestro caso de uso Registro de Usuario, comprobando con assert que no devuelva null.

<br>
<a name="PRUEBASEND"></a>

## Pruebas End-to-End

Las pruebas End-to-End replican el comportamiento de los usuarios con el software, en un entorno de aplicación completo.

Estas pruebas verifican que los flujos que sigue un usuario trabajen como se espera, y pueden ser tan simples como cargar una página web, iniciar sesión, o mucho más complejas, como por ejemplo verificando notificaciones vía email.

Estas son muy útiles, pero son costosas de realizar; y pueden ser difíciles de mantener cuando son automatizadas.

Por tanto, es recomendable tener unas pocas pruebas End-to-End, que resulten claves para nuestra aplicación.

En nuestro proyecto no hemos implementado pruebas End-to-End por falta de tiempo.

