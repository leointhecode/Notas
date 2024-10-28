
**Domain description:**

```
El dominio se explaya en la utilización de postman, se revisan los conceptos claves, procesos para llevar a cabo la creación de peticiones, el análisis de las mismas y su automatización. 
```

**Knowledge Area:** [[Domain -  APIs]]


> [!NOTE] Index
> 1. [[#Introducción]]
> 2. [[#Ventajas de postman]]
> 3. [[#Que es workspace y collections?]]
> 4. [[#¿Cómo crear una petición?]]
> 5. [[#Como analizar las respuestas?]]
> 6. [[#Automatización con postman]]

## Introducción 

Postman es una herramienta de pruebas de API. La interfaz sencilla y fácil de usar ayuda a la hora de documentar, diseñar y probar las APIs. Puedes crear peticiones de puntos finales de API, enviar varios tipos de datos y evaluar respuestas sin esfuerzo con Postman. Su interfaz gráfica de usuario, sencilla e informativa, facilita incluso a los principiantes menos experimentados la interacción con las APIs sin necesidad de profundizar en un código complejo.

## Ventajas de postman

- **Aseguramiento de la calidad**: las pruebas de API mantienen la confianza y la reputación al asegurar un desempeño confiable.

- **Detección temprana de problemas**: las pruebas tempranas de API (“shift left”) identifican y permiten resolver defectos en etapas tempranas.

- **Conservación de recursos**: las pruebas automatizadas de API ahorran tiempo e impulsan la innovación.

- **Iteración rápida**: las pruebas de API en pipeline CI/CD permiten liberaciones frecuentes sin errores.

- **Organización eficiente de las pruebas**: la interfaz de Postman permite crear colecciones reutilizables, lo que mejora la organización y el uso compartido de las pruebas.

- **Integración Continua  sin problemas**: Postman se integra a la perfección con las principales herramientas de integración continua, proporcionando visibilidad de las versiones generadas de API junto con las pruebas y el desarrollo. 

- **Colaboración en tiempo real**: las capacidades de control y colaboración de Postman promueven el intercambio de datos en tiempo real y el trabajo en equipo, reduciendo la duración del ciclo de desarrollo. 

- **Diseño y simulación**: las funcionalidades de diseño y simulación de Postman eliminan la necesidad de configuración inicial del servidor backend, acelerando el desarrollo de la API.

## Que es workspace y collections?

Workspace y Collections son dos conceptos importantes en Postman. Primero, entendamos qué son. 

Workspace es una plataforma colaborativa en la que los desarrolladores pueden organizar, gestionar y colaborar de forma colectiva en pruebas con Postman, proporcionando un área compartida para crear, editar y mantener componentes de API.

Collections le permite agrupar múltiples peticiones, facilitando la gestión y ejecución de escenarios de pruebas con Postman.

## ¿Cómo crear una petición?

Para comenzar con Postman, puedes crear una nueva petición de API según tu espacio de trabajo o workspace preferido. Una vez que hayas elegido el espacio de trabajo, selecciona el tipo de petición. Algunos ejemplos de tipos de peticiones son: GET, POST, PUT, PATCH, DELETE, etc. Las peticiones de tipo GET sirven para recuperar datos del servidor API y DELETE se utiliza para borrar datos. Las peticiones tipo POST para insertar datos, mientras que PUT y PATCH se utilizan para actualizarlos. 

A continuación, introduce un end-point para su prueba con Postman. Un end-point es, básicamente, el punto de comunicación de una API y se trata de una URL o URI.

Luego puedes incluir detalles de parámetros de petición según sea necesario. Postman soporta múltiples métodos de autorización y autenticación, tales como Basic auth, API Key, Bearer Token, OAuth, etc.

Añade los encabezados y el cuerpo a tu petición si es necesario. Los encabezados contienen más información acerca de la petición HTTP que necesitas enviar. También puedes incluir encabezados personalizados.

## Como analizar las respuestas?

Inspecciona la respuesta para asegurarte que corresponde al resultado esperado. Postman ofrece varias vistas, tales como Pretty, Raw y Preview para analizar los datos de forma eficiente. Las respuestas HTTP API en el rango de 200 indican peticiones de API satisfactorias. Si se encuentra en el rango de 200, quiere decir que el servidor ha aceptado y procesado la petición del cliente sin ningún error. Esto confirma que la petición de API se ha completado satisfactoriamente. El rango de 400 indica que el servidor ha entendido la petición del cliente, pero existe un problema con la petición. Un rango de 500 indica errores de servidor. 

## Automatización con postman

Postman ofrece funciones para pruebas automatizadas porque las pruebas manuales requieren más tiempo y esfuerzo. 

La automatización mejorará significativamente tu proceso de pruebas de API. Más importante aún, ayudará a ejecutar pruebas repetidamente, garantizando resultados consistentes y confiables. Aquí te indicamos cómo puedes automatizar una prueba API en Postman.

1. **Selecciona la pestaña "tests"**

Selecciona la pestaña “Tests” de tu petición y vSolo por obtener un código de respuesta en el rango de 200, no se puede considerar que el caso de prueba ha sido completado.

Puedes usar estos snippets no solo para validar el resultado de tu caso de prueba, sino también para probar el rendimiento contra el tiempo de respuesta, validar el resultado, etc.erás múltiples snippets. El caso de prueba será aprobado si el código de respuesta es 200. 

2. **Ejecute las pruebas automatizadas como una Colección**

El Collection Runner de Postman puede emplearse para ejecutar toda la colección de pruebas. Esto ejecutará las peticiones automáticamente como una serie. Allí, puedes configurar datos de pruebas, variables de entorno e iteraciones para simular escenarios del mundo real.

3. **Integración con CI/CD**

En el ciclo de vida de desarrollo, las pruebas de API automatizadas con Postman pueden integrarse con su pipeline CI/CD. Esto garantizará que los cambios añadidos recientemente durante el desarrollo de funciones o la corrección de errores no afecten la funcionalidad actual de la API. Postman permite acceder a los detalles de las fases de construcción en CI/CD, monitorear el estado de prueba y automatización e iniciar nuevos procesos de compilación para su API.

4. **Monitorear el Rendimiento de la API**

Monitorea el rendimiento de la API en el tiempo usando Postman Monitors. Estas ejecuciones programadas rastrean el comportamiento de la API y proporcionan información valiosa sobre tiempos de respuesta, tasas de error y otras métricas