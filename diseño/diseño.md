# Diseño de la aplicación.

## Índice de contenido

**[1. Modelo de clases del Backend.](#BACKEND)**

**[2. Modelo de clases del Frontend.](#FRONTEND)**

**[3. Modelo Entidad/Relación.](#E/R)**

<a name="BACKEND"></a>

## Modelo de clases del Backend

<img src=".\resources\Diagrama de clases de modelo.png" />

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-1 Usuario </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Usuario registrado para acceder a las funciones de la aplicación.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del usuario.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nick
        </td>  
        <td>
            Nombre único para cada usuario registrado en la aplicación. Lo elige él mismo.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Password
        </td>  
        <td>
            Contraseña para acceder a la cuenta de usuario registrado.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Email
        </td>  
        <td>
            Email del usuario registrado.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nombre
        </td>  
        <td>
            Nombre real del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Apellidos
        </td>  
        <td>
            Apellidos reales del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nacionalidad
        </td>  
        <td>
            Nacionalidad del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_Nacimiento
        </td>  
        <td>
            Fecha de nacimiento del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Dirección
        </td>  
        <td>
            Dirección de envio del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Boolean
        </td>
        <td>
            isAdmin
        </td>  
        <td>
            Especifica si el usuario tiene privilegios de Administrador o no.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Foto_perfil
        </td>  
        <td>
            Url de la foto de perfil del usuario.
        </td> 
    </tr>
    <tr>
        <td>
            Lista, List&lt;Foro&gt;
        </td>
        <td>
            Lista_hilos
        </td>  
        <td>
            Lista de hilos creados por el usuario registrado.
        </td> 
    </tr>
    <tr>
        <td>
            Boolean
        </td>
        <td>
           	Baneado
        </td>  
        <td>
            Campo booleano que indicará si el usuario está baneado o no.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-2 Ticket </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Intermediario entre producto y usuario en el que se guardan todos los productos comprados por el usuario.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del ticket.
        </td> 
    </tr>
    <tr>
        <td>
            Date
        </td>
        <td>
            Fecha
        </td>  
        <td>
            Fecha de la compra.
        </td> 
    </tr>
    <tr>
        <td>
            Double
        </td>
        <td>
            Importe
        </td>  
        <td>
            Importe por el que ha salido la compra.
        </td> 
    </tr>
    <tr>
        <td>
           	Integer
        </td>
        <td>
            Uds
        </td>  
        <td>
            Unidades de producto compradas por usuario.
        </td> 
    </tr>
    <tr>
        <td>
            Usuario
        </td>
        <td>
            Usuario
        </td>  
        <td>
            Usuario que compra.
        </td> 
    </tr>
    <tr>
        <td>
            Producto
        </td>
        <td>
            Producto
        </td>  
        <td>
            Producto/s comprado.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-3 Favoritos </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Productos que el usuario añade como favorito.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del producto favorito.
        </td> 
    </tr>
    <tr>
        <td>
            Usuario
        </td>
        <td>
            Usuario
        </td>  
        <td>
            Usuario que añade producto a favorito.
        </td> 
    </tr>
    <tr>
        <td>
            Producto
        </td>
        <td>
            Producto
        </td>  
        <td>
            Producto/s que ha sido añadido a favorito.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-4 Producto </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Producto que la aplicación pone en venta.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del producto.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nombre
        </td>  
        <td>
            Nombre del producto.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Descripcion
        </td>  
        <td>
            Descripción detallada del producto.
        </td> 
    </tr>
    <tr>
        <td>
           	Numérico, Double
        </td>
        <td>
            Precio
        </td>  
        <td>
            Precio del producto en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Stock_disponible
        </td>  
        <td>
            Stock disponible del producto en el almacén.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_creación
        </td>  
        <td>
            Fecha de introducción del producto en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Lista, List&lt;Usuario&gt;
        </td>
        <td>
            Lista_tickets
        </td>  
        <td>
            Lista de tickets que tiene un producto.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-5 Hilo </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Hilo creado en el foro por un usuario para debatir y conversar.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del hilo.
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Id_Creador
        </td>  
        <td>
            Identificador del usuario creador del hilo.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_Creación
        </td>  
        <td>
            Fecha de creación del hilo.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-6 Mensaje </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Mensaje creado por el usuario para un hilo.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del mensaje.
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Id_Autor
        </td>  
        <td>
            Identificador del autor del mensaje.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_Creacion
        </td>  
        <td>
            Fecha de creación del mensaje.
        </td> 
    </tr>
</table>

<br>

<a name="FRONTEND"></a>

## Modelo de clases del Frontend

<img src=".\resources\Diagrama de clases de modelo.png" />

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-1 Usuario </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Usuario registrado para acceder a las funciones de la aplicación.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del usuario.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nick
        </td>  
        <td>
            Nombre único para cada usuario registrado en la aplicación. Lo elige él mismo.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Password
        </td>  
        <td>
            Contraseña para acceder a la cuenta de usuario registrado.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Email
        </td>  
        <td>
            Email del usuario registrado.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nombre
        </td>  
        <td>
            Nombre real del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Apellidos
        </td>  
        <td>
            Apellidos reales del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nacionalidad
        </td>  
        <td>
            Nacionalidad del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_Nacimiento
        </td>  
        <td>
            Fecha de nacimiento del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Dirección
        </td>  
        <td>
            Dirección de envio del usuario registrado en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Boolean
        </td>
        <td>
            isAdmin
        </td>  
        <td>
            Especifica si el usuario tiene privilegios de Administrador o no.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Foto_perfil
        </td>  
        <td>
            Url de la foto de perfil del usuario.
        </td> 
    </tr>
    <tr>
        <td>
            Lista, List&lt;Foro&gt;
        </td>
        <td>
            Lista_hilos
        </td>  
        <td>
            Lista de hilos creados por el usuario registrado.
        </td> 
    </tr>
    <tr>
        <td>
            Boolean
        </td>
        <td>
           	Baneado
        </td>  
        <td>
            Campo booleano que indicará si el usuario está baneado o no.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-2 Ticket </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Intermediario entre producto y usuario en el que se guardan todos los productos comprados por el usuario.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del ticket.
        </td> 
    </tr>
    <tr>
        <td>
            Date
        </td>
        <td>
            Fecha
        </td>  
        <td>
            Fecha de la compra.
        </td> 
    </tr>
    <tr>
        <td>
            Double
        </td>
        <td>
            Importe
        </td>  
        <td>
            Importe por el que ha salido la compra.
        </td> 
    </tr>
    <tr>
        <td>
           	Integer
        </td>
        <td>
            Uds
        </td>  
        <td>
            Unidades de producto compradas por usuario.
        </td> 
    </tr>
    <tr>
        <td>
            Usuario
        </td>
        <td>
            Usuario
        </td>  
        <td>
            Usuario que compra.
        </td> 
    </tr>
    <tr>
        <td>
            Producto
        </td>
        <td>
            Producto
        </td>  
        <td>
            Producto/s comprado.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-3 Favoritos </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Productos que el usuario añade como favorito.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del producto favorito.
        </td> 
    </tr>
    <tr>
        <td>
            Usuario
        </td>
        <td>
            Usuario
        </td>  
        <td>
            Usuario que añade producto a favorito.
        </td> 
    </tr>
    <tr>
        <td>
            Producto
        </td>
        <td>
            Producto
        </td>  
        <td>
            Producto/s que ha sido añadido a favorito.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-4 Producto </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Producto que la aplicación pone en venta.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del producto.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Nombre
        </td>  
        <td>
            Nombre del producto.
        </td> 
    </tr>
    <tr>
        <td>
            Cadena, String
        </td>
        <td>
            Descripcion
        </td>  
        <td>
            Descripción detallada del producto.
        </td> 
    </tr>
    <tr>
        <td>
           	Numérico, Double
        </td>
        <td>
            Precio
        </td>  
        <td>
            Precio del producto en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Stock_disponible
        </td>  
        <td>
            Stock disponible del producto en el almacén.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_creación
        </td>  
        <td>
            Fecha de introducción del producto en la aplicación.
        </td> 
    </tr>
    <tr>
        <td>
            Lista, List&lt;Usuario&gt;
        </td>
        <td>
            Lista_tickets
        </td>  
        <td>
            Lista de tickets que tiene un producto.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-5 Hilo </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Hilo creado en el foro por un usuario para debatir y conversar.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del hilo.
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Id_Creador
        </td>  
        <td>
            Identificador del usuario creador del hilo.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_Creación
        </td>  
        <td>
            Fecha de creación del hilo.
        </td> 
    </tr>
</table>

<br>

<table style="width:100%">
    <tr>
        <th>
            <b>RI-6 Mensaje </b>
        </th>
    </tr>
    <tr>
        <td>
            <b>Autor<b>
        </td>
        <td>Equipo</td>  
    </tr>
    <tr>
        <td>
            <b>Descripción<b>
        </td>
        <td>Mensaje creado por el usuario para un hilo.</td>  
    </tr>
    <tr>
        <td>
            <b>Tipo de dato<b>
        </td>
        <td>
            <b>Nombre<b>
        </td>  
        <td>
            <b>Descripción<b>
        </td> 
    </tr>
    <tr>
        <td>
           Numérico, Integer
        </td>
        <td>
            Id
        </td>  
        <td>
            Identificador del mensaje.
        </td> 
    </tr>
    <tr>
        <td>
            Numérico, Integer
        </td>
        <td>
            Id_Autor
        </td>  
        <td>
            Identificador del autor del mensaje.
        </td> 
    </tr>
    <tr>
        <td>
            Fecha, Date
        </td>
        <td>
            Fecha_Creacion
        </td>  
        <td>
            Fecha de creación del mensaje.
        </td> 
    </tr>
</table>

<br>

<a name="E/R"></a>

## Modelo Entidad/Relación

<img src=".\resources\Diagrama E_R.png"  />

<br>