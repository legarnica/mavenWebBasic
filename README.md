# CREACIÓN DE UNA APLICACIÓN WEB ESTÁNDAR CON SPRING TOOLS.

En esta oportunidad seguimos con la utilización de `maven`; pero ahora pasamos desde una aplicación simple a una WEB. Es decir que utilizaremos un navegador para poder visualizar el resultado de nuestra aplicación y no la consola de nuestro IDE.

## Pasos:
+ Los mismos pasos que creamos en el proyecto simple ubicado en: [https://github.com/elrerag/mavenBasic]. (Hasta la creación del proyecto)
+ Con el proyecto creado, Tenemos un detalle que resolver. El IDE por defecto deja el JRE con Java 1.5, nosotros estamos usando el 1.8, es por eso que debemos indicarle al IDE que use esa versión. Para esto nos vamos `JRE System Library`, hacemos click derecho y nos vamos a propiedades, y seleccionamos la correcta para luego aplicar. (img)
+ Indicamos para que el IDE sepa que no queremos usar el 1.5, lo definimos en 1.8 de ahora en adelante, para esto vamos a: `[project-name] > preferences > Java > Compiler` acá veremos que se encuentra efectivamente en 1.8; pero debemos indicarlo específicamente para el proyecto. Para esto debemos ir dentro de esta misma ventana a `Configure Project Specific Settings...` (img), luego seleccionamos nuestro proyecto. (img).  Veremos una ventana y el 1.5 seleccionado además de unas advertencias. (img). Todo esto se soluciona seleccionando la versión 1.8 (img). Aplicamos y cerramos, se nos aparece una ventana de advertencia, nos advierte que debe volver a construir. La aceptamos. Y hacemos lo mismo con las ventanas que nos queden por cerrar, es decir. Aceptamos y cerramos. De esta forma ya no tendremos advertencias. (img) y podremos seguir con el desarrollo de nuestra aplicación.
+ Lo siguiente es transformar este proyecto en un proyecto web. Para ello debemos ir a: `[project-name] > preferences > Project Facets`, luego hacemos click en `Convert to faceted form...` (img). Seleccionamos `Dinamic Web Module`, Cambiamos la versión a la última, para este ejemplo era la 4.0. (img).  Al seleccionar esta faceta, podemos seleccionar opciones adicionales, como cambiar el nombre de la carpeta contenedora de nuestros archivos web. Hacemos click entonces en `Furher configuration available` (img).  Cambiamos de `WebContent` a `webapp`, ya que acá indicamos lo que compete a la aplicación web. Además de chequear la opción de `generate web.xml deployment descriptor`, de esta forma cuando requiramos este archivo, estará listo. (img). Aplicamos y cerramos. De esta forma podremos ver el nuevo directorio añadido. (img).
+ Asumiendo que ya tenemos agregado un servidor a nuestro IDE, en mi caso `apache 9`, debemos indicarle al IDE que use este servidor (la instalación de dicho servidor no forma parte de este manual). Para esto  `[project-name] > preferences > Java Build Path `. Seleccionamos la pestaña `Libraries > Add Library...`  (img) Seleccionamos `server runtime` Presionamos siguiente y nos debería aparecer el servidor que tenemos integrado a nuestro IDE. En nuestro caso: `Apache Tomcat v9.0` (img). Aplicamos y cerramos.
+ Nos queda entonces crear un archivo `jsp` que contiene el código `html` que veremos en nuestro navegador. Nos situamos en el directorio que se creó `webapp` y creamos un nuevo archivo `jsp`. (img), lo llamamos `index.jsp` y finalizamos.(img), lo que debería tener el siguiente código:

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>

</body>
</html>
```
+ Agregamos el saludo con : `<h1> Hola mundo desde la web </h1>`, es decir que el código debería poder quedar de la siguiente forma:

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
    <h1> Hola mundo desde la web </h1>
</body>
</html>
```

+ Para comprobar los resultados hacemos click derecho sobre el proyecto y seleccionamos `run as > on server`  (img) nos pedirá que seleccionemos de una lista de servidores. Dejamos seleccionado `always use this server when running this project` para que no tengamos que seleccionar el servidor cada vez que ejecutemos la aplicación. (img).
+ En un navegador entonces, al solicitar la siguiente URL: [http://localhost:8080/mavenWebBasic/] podremos ver nuestra app funcionando. (img)

## Conclusiones

Para poder iniciar una aplicación web con Java, necesitamos como hemos visto un servidor. Eclipse posee integración con varios y en este caso se disponía de uno Apache Tomcat. Si la integración con este no es parte de las competencias que posee, no dude en contactarme para enviar un pequeño manual de como hacerlo. Entonces luego de tener integrado el servidor, debemos realizar una serie de pasos antes de poder comenzar a codificar nuestra solución. En un principio y comparado con la facilidad que resulta hacer lo mismo en otro lenguaje, quizás Java no parezca una buena opción; pero debemos pensar en que Java lleva muchos años solucionando problemas de grandes compañías y sin ir en desmedro de los demás lenguajes, al tener tantas opciones en Java es que debemos indicar mediante estas configuraciones qué es lo que necesitamos realmente para el contexto extremadamente versátil que Java nos proporciona. Luego de realizar estas configuraciones iniciales en el día a día de nuestros trabajos, ya no nos parecerá tan “terrible” hacerlo. Por consiguiente, comenzaremos a encontrar el gusto, ese gusto que nos motiva a estar sentados resolviendo puzzle complejos y si tenemos este tan robusto lenguaje de nuestro lado, nosotros y sobre todo la compañía que necesita la solución, puede respirar tranquila que, sea cual sea el escenario al que nos enfrentemos, Java tendrá las herramientas para solucionarlo.
