<div align="center">
<a href="https://matricula.vonex.edu.pe/">
    <img src="logo.png" alt="Logo" width="80" height="80">
  </a>
<h3 align="center">APP MATRICULA</h3>
<p>
Es una aplicación dedicada al registro de inscripciones de estudiantes para la Academia Vonex, Sistema Integrado con la pasarela de pagos Culqi, Emisión de correos con las API de Google y API Peru Dni que obtiene los datos del usuario.
</p>
</div>

</br>

## ÍNDICE
<ul>
    <li><a href="#requerimientos">Requerimientos</a></li>
    <li><a href="#tecnologia">Tecnologías</a></li>
    <li><a href="#librerias">Librerias</a></li>
    <li><a href="#seguridad">Seguridad</a></li>
    <li><a href="#variables">Variables de entorno</a></li>
    <li><a href="#modulos">Módulos</a></li>
    <li><a href="#pasarela">Integración de servicios</a></li>
    <li><a href="#diagrama">Diagrama de flujo</a></li>
  </ul>

</br>

## REQUERIMIENTOS (SERVIDOR)
<b>Php 8.1</b>
```
sudo apt install -y bcmath xml fpm mysql zip intl ldap gd cli bz2 curl mbstring pgsql opcache soap cgi
```
<b>Postgresql</b>
```
sudo apt install postgresql-contrib
```

<b>Headers</b>
```
sudo a2enmod headers
```

</br>

## TECNOLOGÍAS
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/laravel/laravel-plain-wordmark.svg" alt="laravel" width="40" height="40"/> Laravel 10

<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original-wordmark.svg" alt="vuejs" width="40" height="40"/> Vue 3

</br>

## LIBRERIAS
<ul>
    <li>Bootstrap</li>
	<li>Font Awesome</li>
	<li>Axios</li>
	<li>SweetAlert2</li>
	<li>Toastr</li>
	<li>Crypto-js</li>
</ul>

</br>

## SEGURIDAD
<p>
<b>Header always append X-Frame-Options (SERVIDOR)</b><br>
Para prevenir ataques de incrustación de contenido desde otros dominios.
</p>

```
Header always append X-Frame-Options SAMEORIGIN
```

<p>
<b>Header set X-Content-Type-Options (SERVIDOR)</b><br>
Esto ayuda a prevenir ataques de tipo MIME sniffing, donde un navegador intenta adivinar el tipo de contenido de un archivo.
</p>

```
Header set X-Content-Type-Options nosniff
```

<p>
<b>Header set X-XSS-Protection (SERVIDOR)</b><br>
Ayuda a proteger contra ataques de scripting entre sitios (XSS).
</p>

```
Header set X-XSS-Protection "1; mode=block"
```

<p>
<b>Header set Strict-Transport-Security (SERVIDOR)</b><br>
Obliga al navegador a utilizar una conexión segura (HTTPS) en lugar de HTTP.
</p>

```
Header set Strict-Transport-Security "max-age=31536000; includeSubDomains"
```

<p>
<b>Header set Referrer-Policy (SERVIDOR)</b><br>
Significa que el navegador enviará la información de referencia cuando se navega de un sitio seguro (HTTPS) a uno no seguro (HTTP).
</p>
<p>
	
```
Header set Referrer-Policy: "no-referrer-when-downgrade"
```

<b>JSON Web Token (Frontend/Backend)</b><br>
Encriptación de datos para la transmisión de información entre el Frontend y Backend.
</p>

</br>

## VARIABLES DE ENTORNO
<p>
<b>CULQUI_SECRET_KEY:</b> token secreto de culqi.
</p>

<p>
<b>CULQUI_PUBLIC_KEY:</b> token publico de culqi.
</p>

<p>
<b>CULQUI_PREFIJO_ID:</b> prefijo de identificación(id) en las transacciones por matricula de la BD.
</p>

<p>
<b>API_PERU_DNI:</b> token para la conexion con el Api Peru DNI.
</p>

</br>

## MODULOS (PASOS)
<p>
La aplicación cuenta con 3 pasos, En el paso 1 es donde se obtiene los datos del alumno y boleta ya sea con el API Peru dni o manualmente luego en el paso 2 se procede con el registro del ciclo donde al ser completado quedara preinscrito y finalmente el paso 3 se procedera con el pago usando la pasarela de pago Culqi, Una vez completado el pago se generara la matricula, la creacion de su correo y se le enviara un correo con sus credenciales.
</p>
<ul>
	<li>Paso 1: Registro de datos</li>
	<li>Paso 2: Registro de ciclo</li>
	<li>Paso 3: Registro de Pago</li>
</ul>

</br>

## INTEGRACIÓN DE SERVICIOS
<p>
<b>Pasarela de pago</b>
Culqi es una pasarela de pago que facilita el procesamiento de transacciones en línea, ofreciendo seguridad, facilidad de integración y diversas opciones de pago ya sea tarjeta de crédito, débito o Pago efectivo. 
</p>
<p>
<b>API Peru Dni</b>
Es un API que te permite acceder a información relacionada con los ciudadanos peruanos a través de su número de DNI. Esto podría incluir la validación de números de DNI, la obtención de datos básicos de un individuo a partir de su DNI (como nombres, apellidos, direccion, ubigeo, etc)
</p>
<p>
<b>API Google (OAuth)</b>
Una API de Google OAuth permite que los desarrolladores autentiquen usuarios y obtengan autorización para acceder a los datos y recursos de esos usuarios de manera segura y poder gestionar la cuenta en mencion.
</p>

</br>

## DIAGRAMA DE FLUJO

<div align="center">
    <img src="diagrama.jpg" alt="Logo" width="500" height="480">
</div>

</br>

## COLABORADORES DE PROYECTO
Fredy Rojas
