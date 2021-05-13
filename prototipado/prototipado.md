# Prototipado de usuario.

## Introducción

En este apartado hablaremos sobre los diferentes prototipos de la interfaz de la aplicación en su versión más preliminar. Son diseños que como su propio nombre indica, a lo largo del desarrollo cambiarán mucho hasta llegar a su versión final en la fase de despliegue. A continuación, se explicarán las diferentes vistas en diferentes escenarios.

<br>

## Prototipo de interfaz

- **Vista principal**

  <img src=".\resources\INDEX V2.png" />
  
  En esta primera vista, podemos comprobar que de primeras el usuario no estará logueado. Lo tendrá que hacer para poder hacer todas las acciones disponibles de la aplicación menos el consultar que si puede hacerlo sin estar logueado.
  
  Se puede comprobar como de vista principal lo que aparece es toda la gama de productos que existen en el sistema. Por otra parte, el usuario puede desplegar a través de un drawer un submenú con opción al foro. El apartado de noticias se queda como posible mejora de futuro.
  
  <img src=".\resources\INDEX V2 LOGUEADO.png" />
  
  En esta segunda pantalla podemos comprobar que una vez el usuario inicie sesión se le abrirá la posibilidad de poder comprar producto, añadir a favorito o incluso ir al apartado de foro.
  
  En la siguiente pantalla se explicará el prototipo de la vista login. Es de las que mantiene su diseño más parecido al final.
  
  <br>
  
- **Vista Login**

  <img src=".\resources\LOGIN.png" />

  En la pantalla de login podemos ver una vista muy simple en la que el usuario podrá iniciar sesión para poder adquirir esos otros privilegios en la aplicación.

  No se muestra, pero si las credenciales son de administrador obtendrá unos privilegios que el usuario normal no tendrá.

  Por lo demás, nos encontramos con dos campos de texto en el que se meterán los datos del usuario y un botón para realizar la opción de Login. No se muestra en el prototipo, pero se podrá también iniciar sesión desde Google.

  <br>

- **Vistas Detalles del producto**

  <img src=".\resources\DETALLES PRODUCTO SIN LOGIN.png" />

  Sin estar logueado el usuario puede entrar a ver más en detalle el producto. Esto lo llevará a la pantalla de arriba en la que se puede ver la imagen, descripción, precio, título... del producto.

  <img src=".\resources\DETALLES PRODUCTO LOGUEADO.png" />

  En esta segunda imagen nos encontramos lo mismo que en la anterior, pero con los permisos al habernos logueado (Comprar Producto, añadir a favorito...).

  <br>

- **Vistas del Foro**

  <img src=".\resources\FORO.png" />

  Al clickar sobre la opción de foro en el Drawer de la vista principal, el usuario logueado llega a la pantalla que vemos arriba.

  Se puede ver una tabla que contiene tres partes principales. Los hilos / temas a los que puede entrar, los mensajes que hay dentro de cada hilo y el usuario que creó ese hilo.

  Si clickamos sobre un hilo / tema navegará hasta la pantalla del hilo en concreto. En esta primera pantalla de foro el usuario normal podrá entrar en un hilo y/o crear un nuevo hilo. El administrador podrá hacer lo anterior más la acción también aparte de eliminar un hilo.

  <img src=".\resources\TEMA CONCRETO FORO.png" />

  En esta segunda pantalla, vemos ya un hilo en concreto. Por lo tanto, pdemos comprobar los diferentes mensajes de otros usuarios y estos usuarios en sí.

  Las acciones que podemos hacer en esta vista como usuario normal será el poder crear un nuevo mensaje. Como administrador podrá revisar todos estos mensaje y también crear uno o eliminarlo.

  <br>