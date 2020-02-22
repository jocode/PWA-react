# Curso de PWA con Recat en Platzi

Este repositorio contiene todo el contenido del curso a medida que construimos una app para ver recetas con la API de MealDB.

Hay un branch por clase para que puedas navegar con facilidad el curso.

#

## ¿Qué es una PWA?

**¿Cómo es la web hoy?**

- **Spoiler Alert**: No funciona muy bien en mobile.
- Más del 50% de nuestros usuarios está en mobile.
- Tenemos malas conexiones en los dispositivos móviles, conexiones tipo 3G y - LTE no son particularmente confiables. Esto genera que un sitio promedio tarda 14 segundos en cargar en mobile.
- La UX no es solamente el diseño de nuestra app, tiene que ver con que tan rápido funciona nuestra aplicación en el mundo real, con un teléfono que tiene una conexión mala.

Hay estudios que demuestran la importancia de lograr que tu sitio funcione rápidamente en dispositivos móviles:
• 50% de los usuarios se van de un sitio que tarda más de 3 segundos en cargar.
• Cada segundo de demora nos cuesta un 5-10% de nuestras ventas.

## Google Lighthouse

Es una herramienta oficial de Google que viene con Chrome, con la cual podemos hacer un diagnóstico a una Web App. Estos diagnósticos se centran en Performance y Accesibilidad, pero también tiene una herramienta para diagnosticar si nuestra Web App se considera una PWA o no y que pasos debemos de tomar para que lo sea.

Lighthouse no sustituye hacer pruebas con un dispositivo móvil real, siempre realiza pruebas en un dispositivo móvil.

El diagnostico de Performance nos muestra dos de los conceptos más importantes en performance: First meaningful Paint y First interactive.

First meaningful Paint o primer pintado significativo, esto señala cuanto tiempo tardo el navegador en renderizar la aplicación de una forma que tenga sentido. Generalmente queremos que este situado entre 1 y 2 segundos.

First interactive o primera interacción, señala el tiempo cuando ya se cargó React, inicializo la aplicación y que podamos correr comandos dentro de la aplicación.

¿Cómo bajamos estos tiempos?

Para bajar el Time To First Meaningful Paint podemos hacer Server Side Rendering, reducir el tamaño de nuestro HTML y CSS o simplemente teniendo servidores más rápidos.
El Time To Interactive tiene mucho que ver con el framework que estemos utilizando, usualmente queremos que tarde menos de 5 segundos.
