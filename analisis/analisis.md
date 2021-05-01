# Análisis de la aplicación.

## Índice de contenido

**[1. Gestión de usuarios.](#USUARIOS)**

**[2. Despliegue de productos.](#PRODUCTOS)**

**[3. Gestion de foro.](#FORO)**

<br>
<a name="USUARIOS"></a>

## Gestión de usuarios

### Diagrama de casos de uso.

<img src=".\resources\Gestiondeusuarios.png"/>

### Descripción de casos de uso.

- **Registro de Usuarios**

  <table style="width:100%">
      <tr>
          <td>
              <b>ID: </b>
          </td>
          <td>CU-1</td>
      </tr>
    	<tr>
          <td>
              <b>Nombre: </b>
          </td>
          <td>Registro de Usuarios</td>
     	</tr>
      <tr>
          <td>
              <b>Equipo/Individual<b>
          </td>
          <td>Individual: José Antonio</td>  
      </tr>
      <tr>
          <td>
              <b>Descripción:</b>
          </td>
          <td>Cómo nuevo usuario quiero registrarme en el sistema.</td>
      </tr>
      <tr>
          <td>
              <b>Actores:</b>
          </td>    
          <td>Cliente / Administrador</td>  
      </tr>  
      <tr>  
          <td>
              <b>Precondiciones:</b>
          </td>  
          <td>Ninguna</td>  
      </tr>    
      <tr>  
          <td>
              <b>Curso normal:</b>
          </td>  
          <td>1. El nuevo usuario rellena el formulario de registro.<br>
  			2. El sistema valida que han sido introducidos todos los datos.<br>
  			3. El sistema guarda la información del usuario.<br>
  			4. El usuario ve en pantalla un mensaje que ha sido registrado con éxito.
          </td>  
      </tr> 
      <tr>  
          <td>
              <b>Postcondiciones:</b>
          </td>  
          <td>El usuario queda registrado correctamente.</td>
      </tr>  
      <tr>  
          <td>
              <b>Alternativas/Excepciones:</b>
          </td>  
          <td>3. Al intentar cumplirse ese guardado, no se realiza por lo que salta un error.<br><br>
          </td>
      </tr> 
  </table>

<br>

- **Iniciar Sesión**

  <table style="width:100%">
      <tr>
          <td>
              <b>ID: </b>
          </td>
          <td>CU-2</td>
      </tr>
    	<tr>
          <td>
              <b>Nombre: </b>
          </td>
          <td>Iniciar Sesión</td>
     	</tr>
      <tr>
          <td>
              <b>Equipo/Individual<b>
          </td>
          <td>Individual: José Antonio</td>  
      </tr>
      <tr>
          <td>
              <b>Descripción:</b>
          </td>
          <td>Cómo cliente / administrador quiero acceder al sistema.</td>
      </tr>
      <tr>
          <td>
              <b>Actores:</b>
          </td>    
          <td>Cliente / Administrador</td>  
      </tr>  
      <tr>  
          <td>
              <b>Precondiciones:</b>
          </td>  
          <td>El usuario debe de estar registrado en el sistema previamente.</td>  
      </tr>    
      <tr>  
          <td>
              <b>Curso normal:</b>
          </td>  
          <td>1. El usuario pone su usuario y contraseña.<br>
  			2. El sistema valida que los datos introducidos son correctos.<br>
  			3. El usuario entra en el sistema.<br>
              &nbsp;&nbsp;3.1. Extends Consultar Perfil Usuario<br>
              &nbsp;&nbsp;3.2. Extends Recuperar Lista de Usuarios<br>
              &nbsp;&nbsp;3.3. Extends Añadir Producto<br>
              &nbsp;&nbsp;3.4. Extends Consultar Producto Admin<br>
              &nbsp;&nbsp;3.5. Crear Foro<br>
              &nbsp;&nbsp;3.6. Consultar Foro<br>
              &nbsp;&nbsp;3.6. Borrar Foro<br>
          </td>  
  </tr> 
  <tr>  
      <td>
          <b>Postcondiciones:</b>
      </td>  
      <td>El usuario ve su pantalla correspondiente y queda logueado.</td> 
  </tr>  
  <tr>  
      <td>
          <b>Alternativas/Excepciones:</b>
      </td>  
      <td>2.1. El sistema detecta que los datos introducidos son incorrectos.
          2.2. Vuelve al paso 1.
      </td>
  </tr>
  </table>


  <br>

- **Consultar Perfil Usuario**

  <table style="width:100%">
      <tr>
          <td>
              <b>ID: </b>
          </td>
          <td>CU-3</td>
      </tr>
    	<tr>
          <td>
              <b>Nombre: </b>
          </td>
          <td>Consultar Perfil Usuario</td>
     	</tr>
      <tr>
          <td>
              <b>Equipo/Individual<b>
          </td>
          <td>Individual: José Antonio</td>  
      </tr>
      <tr>
          <td>
              <b>Descripción:</b>
          </td>
          <td>El usuario podrá ver en una pantalla de perfil todos sus datos.</td>
      </tr>
      <tr>
          <td>
              <b>Actores:</b>
          </td>    
          <td>Cliente / Administrador</td>  
      </tr>  
      <tr>  
          <td>
              <b>Precondiciones:</b>
          </td>  
          <td>El usuario deberá estar registrado y/o logueado.</td>  
      </tr>    
      <tr>  
          <td>
              <b>Curso normal:</b>
          </td>  
          <td>1. El usuario pulsa sobre la opción Mis Datos.<br>
              2. El sistema le lleva a la pantalla de su perfil donde se encuentran sus datos.<br>
              3. El usuario puede ver sus datos.
          </td>  
      </tr> 
      <tr>  
          <td>
              <b>Postcondiciones:</b>
          </td>  
          <td>El usuario acaba en la pantalla de su perfil donde están sus datos. 
          </td>
      </tr>  
      <tr>  
          <td>
              <b>Alternativas/Excepciones:</b>
          </td>  
          <td>1. El sistema no devuelve la página por algún error de conexión.<br>
              3. El usuario no puede ver los datos por errores.
          </td>
      </tr> 
  </table>

  

  <br>

- **Recuperar Lista de Usuarios**

  <table style="width:100%">
      <tr>
          <td>
              <b>ID: </b>
          </td>
          <td>CU-4</td>
      </tr>
    	<tr>
          <td>
              <b>Nombre: </b>
          </td>
          <td>Recuperar Lista de Usuarios</td>
     	</tr>
      <tr>
          <td>
              <b>Equipo/Individual<b>
          </td>
          <td>Individual: José Antonio</td>  
      </tr>
      <tr>
          <td>
              <b>Descripción:</b>
          </td>
          <td>El administrador puede ver todos los usuarios que están registrados en el sistema.</td>
      </tr>
      <tr>
          <td>
              <b>Actores:</b>
          </td>    
          <td>Sistema</td>  
      </tr>  
      <tr>  
          <td>
              <b>Precondiciones:</b>
          </td>  
          <td>El usuario deberá estar registrado y/o logueado.</td>  
      </tr>    
      <tr>  
          <td>
              <b>Curso normal:</b>
          </td>  
          <td>1. El sistema recupera la lista de usuarios del usuario que accede a la gestion de amigos.
          </td>  
      </tr> 
      <tr>  
          <td>
              <b>Postcondiciones:</b>
          </td>  
          <td>1. El administrador obtiene la lista completa de todos los usuarios que están registrados.<br>
              &nbsp;&nbsp;1.1. Modificar Usuarios<br>
              &nbsp;&nbsp;1.2. Suspender Usuarios<br>
              &nbsp;&nbsp;1.3. Eliminar Usuarios<br>
          </td> 
      </tr>  
      <tr>  
          <td>
              <b>Alternativas/Excepciones:</b>
          </td>  
          <td>Ninguna.
          </td>
      </tr> 
  </table>


  <br>

- **Modificar Usuarios**

  <table style="width:100%">
      <tr>
          <td>
              <b>ID: </b>
          </td>
          <td>CU-5</td>
      </tr>
    	<tr>
          <td>
              <b>Nombre: </b>
          </td>
          <td>Modificar Usuarios</td>
     	</tr>
      <tr>
          <td>
              <b>Equipo/Individual<b>
          </td>
          <td>Individual: José Antonio</td>  
      </tr>
      <tr>
          <td>
              <b>Descripción:</b>
          </td>
          <td>El administrador modifica los usuarios de la aplicación.</td>
      </tr>
      <tr>
          <td>
              <b>Actores:</b>
          </td>    
          <td>Administrador</td>  
      </tr>  
      <tr>  
          <td>
              <b>Precondiciones:</b>
          </td>  
          <td>El administrador deberá haber recuperado la lista de usuarios.</td>  
      </tr>    
      <tr>  
          <td>
              <b>Curso normal:</b>
          </td>  
          <td>1. El administrador entra en la cuenta del usuario.<br>
  			2. Señala la opción de modificar sus datos.<br>
  			3. Realiza los cambios pertinentes.<br>
  			4. Los cambios se han registrado correctamente.<br>
          </td>  
  </tr> 
  <tr>  
      <td>
          <b>Postcondiciones:</b>
      </td>  
      <td>El administrador habrá modificado correctamente el/los dato/s de el/los usuario/s.
      </td>
  </tr>  
  <tr>  
      <td>
          <b>Alternativas/Excepciones:</b>
      </td>  
      <td>4. El tipo de dato introducido en algún campo al modificar el perfil es incorrecto, no tiene el formato correcto o es 			demasiado largo o corto.
      </td>
  </tr> 
  </table>    


  <br>

- **Suspender Usuarios**

  <table style="width:100%">
      <tr>
          <td>
              <b>ID: </b>
          </td>
          <td>CU-6</td>
      </tr>
    	<tr>
          <td>
              <b>Nombre: </b>
          </td>
          <td>Suspender Usuarios</td>
     	</tr>
      <tr>
          <td>
              <b>Equipo/Individual<b>
          </td>
          <td>Individual: José Antonio Busto</td>  
      </tr>
      <tr>
          <td>
              <b>Descripción:</b>
          </td>
          <td>El administrador suspende temporalmente a usuarios de la aplicación.</td>
      </tr>
      <tr>
          <td>
              <b>Actores:</b>
          </td>    
          <td>Administrador</td>  
      </tr>  
      <tr>  
          <td>
              <b>Precondiciones:</b>
          </td>  
          <td>Ser administrador y acceder a la aplicación.</td>  
      </tr>    
      <tr>  
          <td>
              <b>Curso normal:</b>
          </td>  
          <td>1. El administrador hace clic en administrar usuarios.<br>
      		2. Se abrirá una vista con la lista de usuarios del sistema.<br>
  			3. el administrador hará clic en el usuario deseado y hará clic en suspender temporalmente.<br>
  			4. Se realiza la suspensión correctamente.<br>
          </td>  
      </tr> 
      <tr>  
          <td>
              <b>Postcondiciones:</b>
          </td>  
          <td>Se suspende temporalmente al usuario deseado por el administrador.
          </td>
      </tr>  
      <tr>  
          <td>
              <b>Alternativas/Excepciones:</b>
          </td>  
          <td>Ninguna.
          </td>
      </tr>
  </table>


  <br>

- **Eliminar Usuarios**

  <table style="width:100%">
      <tr>
          <td>
              <b>ID: </b>
          </td>
          <td>CU-7</td>
      </tr>
    	<tr>
          <td>
              <b>Nombre: </b>
          </td>
          <td>Eliminar Usuarios</td>
     	</tr>
      <tr>
          <td>
              <b>Equipo/Individual<b>
          </td>
          <td>Individual: José Antonio</td>  
      </tr>
      <tr>
          <td>
              <b>Descripción:</b>
          </td>
          <td>El administrador quiere dar de baja a un usuario del sistema.</td>
      </tr>
      <tr>
          <td>
              <b>Actores:</b>
          </td>    
          <td>Administrador</td>  
      </tr>  
      <tr>  
          <td>
              <b>Precondiciones:</b>
          </td>  
          <td>El usuario debe de estar registrado en el sistema.</td>  
      </tr>    
      <tr>  
          <td>
              <b>Curso normal:</b>
          </td>  
          <td>1. El administrador selecciona la opción de “eliminar usuario”.<br>
  			2. El sistema elimina a dicho usuario.<br>
  			3. El administrador ve en pantalla que el usuario ha sido eliminado del sistema.<br>
          </td>  
      </tr> 
      <tr>  
          <td>
              <b>Postcondiciones:</b>
          </td>  
          <td>El administrador ha eliminado al usuario del sistema.
          </td>
      </tr>  
      <tr>  
          <td>
              <b>Alternativas/Excepciones:</b>
          </td>  
          <td>2.1. El sistema pierde la conexión y no puede eliminar al usuario.
          </td>
      </tr>
  </table>

<br>
<a name="PRODUCTOS"></a>

## Gestión de productos

### Diagrama de casos de uso.

<img src=".\resources\Gestióndeproductos.png" />

### Descripción de casos de uso.

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-8</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Consultar producto</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El cliente consulta el producto deseado en la página.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Cliente</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Ninguno.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El cliente selecciona un producto de la pagina principal haciendo clic en el. 
            <br>2. El sistema muestra al usuario el producto en una nueva vista.  
            <br>&nbsp;&nbsp;2.1. Extends Comprar producto.
            <br>&nbsp;&nbsp;2.2. Extends Reservar Producto.
            <br>&nbsp;&nbsp;2.2. Extends Añadir a deseados.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El usuario accede a la pagina del producto con su información.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>  Ninguna. <br>
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-9</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Comprar producto</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El cliente compra el producto deseado. </td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Cliente</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Estar registrado como usuario.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El usuario hace clic en comprar.
            <br>2. Include Iniciar sesion.
            <br>3. El sistema pide la dirección, el sistema de pago que quiere el usuario y la información necesaria.
            <br>4. El usuario introduce todos los datos necesarios.
            <br>5. Se realiza la compra correctamente.
            <br>6. Include Registrar ganancias.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El usuario compra satisfactoriamente el producto deseado.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>5. El sistema notifica al usuario que se ha introducido mal algún dato.<br>
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-10</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Reservar producto</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El cliente reserva el producto para la fecha de lanzamiento.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Cliente</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Estar registrado como usuario.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El usuario hace clic en reservar.
            <br>2. Include Iniciar sesion.
            <br>3. El sistema pide la dirección, el sistema de pago que quiere el usuario y la información necesaria.
            <br>4. El usuario introduce todos los datos necesarios.
            <br>5. Se realiza la reserva correctamente.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El usuario reserva el producto satisfactoriamente.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>5. El sistema notifica al usuario que se ha introducido mal algún dato.<br>
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-11</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Añadir a deseados</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El cliente añade a su lista de deseados el producto seleccionado.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Cliente</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Estar registrado como usuario.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El usuario hace clic en añadir a lista de deseados.
            <br>2. Include Iniciar sesion.
            <br>3. Se introduce el producto correctamente en su lista de deseados.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El usuario añade a su lista de deseados el producto correctamente.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna.
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-12</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Registrar ganancias</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El sistema registra en la base de datos la ganancia por el producto vendido.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Sistema</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber comprado como cliente un producto.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. Include Comprar producto.
            <br> 2. El sistema accede al precio del producto y añade a la base de datos de ganancias el 60% del precio total del 				producto como beneficio.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El sistema añade el beneficio obtenido del producto vendido a la base de datos.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna. <br>
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-13</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Añadir producto</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El administrador añade un producto a la base de datos que puede ser comprado por el cliente.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion como administrador.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El administrador hace clic en añadir producto en la vista de administrador.
            <br>2. El sistema muestra la ventana de añadir producto con los campos a rellenar.
            <br>3. El administrador rellena todos los campos necesarios y hace clic en publicar.
            <br>4. El producto es publicado correctamente.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El administrador añade en la tienda un producto correctamente.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>4. El sistema notifica al administrador que hay algun fallo en la cumplimentación de campos del producto. <br>
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-14</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Consultar producto Admin</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El administrador consulta un producto.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion como administrador.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El administrador hace clic en el producto que quiere ver en la vista de administrador.
            <br>2. El sistema muestra la ventana del producto conla información.
            <br>&nbsp;&nbsp;2.1. Extends Retirar producto.
            <br>&nbsp;&nbsp;2.2. Extends Editar producto.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El administrador consulta correctamente el producto deseado.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna.
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-15</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Retirar producto</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El administrador retira un producto.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion como administrador.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El administrador hace clic en retirar producto en la página del producto.
            <br>2. El sistema muestra al administrador una advertencia de estar seguro de borrar el producto.
            <br>3. El administrador hace clic en si.
            <br>4. El producto es borrado correctamente y el sistema redirecciona al administrador a la pagina principal.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El administrador elimina el producto correctamente.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna.
        </td>
    </tr> 
</table>

<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-16</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Editar producto</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Individual: Manuel</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El administrador edita un producto.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion como administrador.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El administrador hace clic en editar producto en la página del producto.
            <br>2. El sistema muestra al administrador una nueva ventana con los campos del producto.
            <br>3. El administrador edita los campos deseados y hace clic en editar.
            <br>4. El producto es editado correctamente.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td>El administrador edita el producto correctamente.<br>  
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>4. El sistema notifica al administrador que hay algun campo no valido introducido.
        </td>
    </tr> 
</table>

<br>
<a name="FORO"></a>

## Gestión de foro

### Diagrama de casos de uso.

<img src=".\resources\Gestióndeforo.png" />

### Descripción de casos de uso.

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-17</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Crear foro</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El cliente/administrador crea un foro.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Cliente/administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesión.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. En la ventana de foros, el cliente hace clic en crear foro.
            <br>2. El sistema muestra una nueva ventana con campos a rellenar.
            <br>3. El cliente rellena los campos necesarios y hace clic en crear.
            <br>4. El foro es creado correctamente.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td> El cliente/administrador crea correctamente un foro.
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>4. El sistema notifica al cliente/administrador que hay algun campo no valido.
        </td>
    </tr> 
</table>


<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-18</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Consultar foro</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El cliente/administrador accede a un foro ya creado previamente.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Cliente/administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El cliente hace clic en el foro deseado.
            <br>2. El cliente accede al foro seleccionado.
            <br> &nbsp;&nbsp;2.1. Extends Enviar mensaje.
            <br> &nbsp;&nbsp;2.2. Extends Eliminar mensaje.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td> El cliente/administrador accede al foro deseado.
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna.
        </td>
    </tr> 
</table>


<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-19</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Enviar mensaje</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El cliente/administrador envia un mensaje por el foro.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Cliente/administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion y accedido a un foro.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El cliente introduce el mensaje que desea enviar y hace clic en enviar.
            <br>2. El sistema envia el mensaje al foro correctamente.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td> El cliente/administrador envia el mensaje correctamente.
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna.
        </td>
    </tr> 
</table>


<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-20</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Borrar foro</td>
   	</tr>
    <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El administrador elimina un foro seleccionado.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El administrador hace clic en el foro deseado.
            <br>2. El admnistrador hace clic en eliminar.
            <br>3. El sistema muestra al administrador una advertencia de estar seguro de borrar el producto.
            <br>4. El administrador hace clic en si.
            <br>5. El producto es borrado correctamente y el sistema redirecciona al administrador a la pagina principal.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td> El administrador elimina el foro correctamente.
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna.
        </td>
    </tr> 
</table>


<br>

<table style="width:100%">
    <tr>
        <td>
            <b>ID: </b>
        </td>
        <td>CU-21</td>
    </tr>
  	<tr>
        <td>
            <b>Nombre: </b>
        </td>
        <td>Eliminar mensaje</td>
   	</tr>
   <tr>
        <td>
            <b>Equipo/Individual<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción:</b>
        </td>
        <td>El administrador elimina un mensaje del foro.</td>
    </tr>
    <tr>
        <td>
            <b>Actores:</b>
        </td>    
        <td>Administrador</td>  
    </tr>  
    <tr>  
        <td>
            <b>Precondiciones:</b>
        </td>  
        <td>Haber iniciado sesion y accedido a un foro.</td>  
    </tr>    
    <tr>  
        <td>
            <b>Curso normal:</b>
        </td>  
        <td>1. El administrador eliminar el mensaje que desea haciendo clic en un boton al lado del mensaje.
            <br>2. El sistema elimina correctamente el mensaje del foro.
        </td>  
    </tr> 
    <tr>  
        <td>
            <b>Postcondiciones:</b>
        </td>  
        <td> El administrador elimina el mensaje correctamente.
        </td>
        </td>  
    </tr>  
    <tr>  
        <td>
            <b>Alternativas/Excepciones:</b>
        </td>  
        <td>Ninguna.
        </td>
    </tr> 
</table>

<br>