# Curso de PWA con Recat en Platzi

Este repositorio contiene todo el contenido del curso a medida que construimos una app para ver recetas con la API de MealDB.

## ¿Qué es una PWA?

**¿Cómo es la web hoy?**

- **Spoiler Alert**: No funciona muy bien en mobile.
- Más del 50% de nuestros usuarios está en mobile.
- Tenemos malas conexiones en los dispositivos móviles, conexiones tipo 3G y - LTE no son particularmente confiables. Esto genera que un sitio promedio tarda 14 segundos en cargar en mobile.
- La UX no es solamente el diseño de nuestra app, tiene que ver con que tan rápido funciona nuestra aplicación en el mundo real, con un teléfono que tiene una conexión mala.

Hay estudios que demuestran la importancia de lograr que tu sitio funcione rápidamente en dispositivos móviles:

- 50% de los usuarios se van de un sitio que tarda más de 3 segundos en cargar.
- Cada segundo de demora nos cuesta un 5-10% de nuestras ventas.

## Google Lighthouse

Es una herramienta oficial de Google que viene con Chrome, con la cual podemos hacer un diagnóstico a una Web App. Estos diagnósticos se centran en Performance y Accesibilidad, pero también tiene una herramienta para diagnosticar si nuestra Web App se considera una PWA o no y que pasos debemos de tomar para que lo sea.

Lighthouse no sustituye hacer pruebas con un dispositivo móvil real, siempre realiza pruebas en un dispositivo móvil.

El diagnostico de Performance nos muestra dos de los conceptos más importantes en performance: First meaningful Paint y First interactive.

First meaningful Paint o primer pintado significativo, esto señala cuanto tiempo tardo el navegador en renderizar la aplicación de una forma que tenga sentido. Generalmente queremos que este situado entre 1 y 2 segundos.

First interactive o primera interacción, señala el tiempo cuando ya se cargó React, inicializo la aplicación y que podamos correr comandos dentro de la aplicación.

- [Deployment app react](https://create-react-app.dev/docs/deployment/)

**¿Cómo bajamos estos tiempos?**

Para bajar el Time To First Meaningful Paint podemos hacer Server Side Rendering, reducir el tamaño de nuestro HTML y CSS o simplemente teniendo servidores más rápidos.
El Time To Interactive tiene mucho que ver con el framework que estemos utilizando, usualmente queremos que tarde menos de 5 segundos.

## Creando un Web Manifest

En esta clase vamos a ver cómo implementar la funcionalidad de Add to Homescreen.

**Nota IMPORTANTE:**

Al momento de crear este curso esta saliendo Chrome 68, dicha versión va a cambiar el comportamiento del Add to Homescreen sutilmente.
create-react-app nos da un Web Manifest pre armado el cual debemos configurar. Todo lo que tiene que ver con nuestro Web Manifest está dentro de los archivos index.html y manifest.json de la carpeta public de nuestro proyecto.

Por el momento vamos a trabajar dentro del archivo manifest.json, en el podemos ver varios atributos, los cuales son:

- **`short_name`**: Es el nombre que se utiliza en la Homescreen.
- **`name`**: Es el nombre de nuestra aplicación.
- **`icons`**: Especifica un array de imágenes que servirán como iconos de la aplicación. Cambiaremos el “favicon.ico” por “icon.png”, especificamos el tamaño a 512x512 y el tipo a “image/png”.
- **`start_url`**: Nos indica en que página comienza nuestra aplicación, por compatibilidad siempre conviene que sea “/” en lugar de “./index.html”.
- **`display`**: Define el modo de visualización para la aplicación. Standalone significa que la aplicación puede correr por su misma.
- **`theme_color`**: Define qué color vamos a usar en la barra de tareas de Android para que combine con nuestra aplicación.
- **`related_applications`**: Sirve si queremos que Chrome en el Add to Homescreen recomiende una aplicación del Store.

Para probar nuestro Add to Homescreen debemos tener en cuenta que un requisito fundamental de las PWA es que todo funcione con HTTPS.

Nuestra aplicación por defecto es fullscreen, así que NO OLVIDES de brindar un camino al home.

En iOS necesitamos añadir alguna metadata al index.html de nuestro proyecto. Al momento de probar nuestra aplicación en iOS nos daremos cuenta de que el Add to Homescreen en este caso debe ser añadido manualmente por el usuario.

_Para más información ver (Manifest)[https://developer.mozilla.org/en-US/docs/Web/Manifest]_

Con el manifest ya lo podríamos colocar en la HomeScreen como PWA. Recordar ejecutar el análisis con **Audit** en chrome.

**[ngrok](https://ngrok.com/)** nos permite crear una conexión https, para eso debemos descargar el programa.

Para ello ejecutamos el programa y le indicamos los siguientes comandos

- **`ngrok http {port}`**

En nuestro caso como se usa el puerto 5000 como servidor, colocamos

- **`ngrok http 5000`**

## Implementar el Manifest

Para finalizar este módulo pon a prueba lo aprendido sobre el Web Manifest y Google Lighthouse. Prueba con diferentes colores en el Web Manifest, experimenta con todas las opciones que puedes poner en el documento. En el mundo real, particularmente con proyectos complejos, nuestra PWA vendrá acompañada de otras aplicaciones móviles por lo cual te servirá ir practicando con la propiedad “related_applications” para vincular dichas aplicaciones.
