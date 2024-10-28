 
**Domain description:**

```
El dominio explica ls definición del testeo de APIs, su funcionalidad, metodologias usadas y software que se usa en la industria. 
```

**Knowledge Area:** [[Domain - Testing & QA]]


> [!NOTE] Index
> 1. [[#Introducción]]
> 2. [[#La logica del API testing]]
> 3. [[#Tipos de testeo en APIs]]
> 4. [[#Software]]

## Introducción 

El testeo de APIs es un tipo de testeo de software, con la particularidad de que nos enfocamos en la creacion de casos de prueba para *Application Programming Interfaces* (APIs), suele ser parte de integration testing para determinar si cumple las expectativas, funcionalidad, performance y seguridad (los cuales son tambien los tipos de testeo que se hacen en el test de APIs).

Actualmente, el API testing es considerado critico en la automatizacion de casos de prueba debido a que la API es la interfaz primaria hacia la logica de la aplicacion y porque los casos de prueba de GUI son complicados y caros de mantener con los cortos ciclos de desarrollo y cambios frecuentes que involucran los desarrollos agiles.

## La logica del API testing

El testeo de APIs involucra la creacion de casos de prueba en un ambiente aislado, asi como parte de las transacciones E2E del testing de integracion. Mas alla de las API RESTful, estas transacciones incluyen multiples tipos de endpoint como...

- Servicios web
- ESBs
- bases de datos
- mainframes
- UIs web

El testeo de APIs se encargara de revisar que las APIs regresen respuestas adecuadas para un rango amplio y fehaciente de requests, igualmente revisan que las reacciones para casos limites como fallas, ingresos inesperados, tiempos de respuesta adecuados y una respuesta segura a potenciales ciberataques.

## Tipos de testeo en APIs

- **Artificial Inteligence** Puede generar automáticamente casos de prueba, identificar posibles problemas y analizar los resultados de las pruebas mediante el aprendizaje automático para identificar patrones y anomalías.

- **Smoke test** - Esta es una prueba preliminar que verifica si las funciones más cruciales de una API funcionan correctamente e identifica cualquier problema importante antes de realizar pruebas adicionales.

- **Functional testing** - Este tipo de prueba valida un sistema de software contra sus requisitos funcionales proporcionando entrada y verificando la salida. Se centra principalmente en las pruebas de caja negra y no se preocupa por el código fuente.

- **Black box testing** - Este es un tipo de prueba en el que el evaluador interactúa con la API sin conocer su funcionamiento interno. El evaluador proporciona entrada y observa la salida generada por la API para identificar cómo responde a las acciones esperadas e inesperadas del usuario.

- **Unit testing** - Esto prueba las partes más pequeñas de una aplicación, llamadas unidades, para verificar su correcto funcionamiento. En las pruebas de API, esto incluye probar puntos finales individuales con una sola solicitud.

- **Interoperability testig** - Esta prueba verifica si una API puede interactuar con otros componentes y sistemas de software sin problemas de compatibilidad. Esto se aplica a las API SOAP.

- **Reliability testing** - Esto prueba las API para determinar si cumplen con las expectativas de funcionalidad, confiabilidad, rendimiento y seguridad. Su objetivo es garantizar que la API funcione de manera consistente como se espera.

- **Validation testing** - Esto confirma que el software coincide con los requisitos comerciales y si las pruebas de API coinciden con los resultados esperados. Está estrechamente relacionado con las pruebas de aceptación del usuario.

- **Runtime error detection** - Esto evalúa la ejecución real de una API y se enfoca en la supervisión, los errores de ejecución, las fugas de recursos y la detección de errores. Los errores detectados se corrigen para evitar fallas en tiempo de ejecución.

- **Fuzzing** - Esta prueba transmite entrada aleatoria, inválida o inesperada a una API para encontrar errores y defectos desconocidos. Un fuzzer de API genera entradas de prueba y secuencias de solicitudes a la API y registra la respuesta para ver si se descubren errores o vulnerabilidades de seguridad.

- **Load testing** - Este tipo de prueba simula cargas de trabajo del mundo real para ver cómo funciona un sistema o una aplicación. El objetivo es encontrar cuellos de botella y determinar el número máximo de usuarios o transacciones que puede manejar el sistema.

- **Performance testing** - Este tipo de prueba evalúa cómo funciona una API bajo ciertas condiciones para evaluar la capacidad de la API para manejar cargas altas y mantener altos niveles de rendimiento. Hay dos tipos principales de pruebas de rendimiento de API: pruebas funcionales y pruebas de carga.

- **Security testing** - Esto verifica vulnerabilidades en las API para encontrar y corregir brechas de seguridad. Implica imitar las acciones de los piratas informáticos para encontrar errores y evitar que los atacantes accedan o interrumpan la API o sus datos.

- **Penetration testing** - Se utiliza la piratería ética para evaluar la seguridad del diseño de una API. Un pentester externo encuentra vulnerabilidades en las integraciones de API debido a la lógica empresarial incorrecta o problemas de programación para identificar vulnerabilidades de seguridad que los atacantes podrían explotar.

- **WS Compliance testing** Estas pruebas se aplican a las API SOAP y aseguran la implementación correcta de estándares como WS-Addressing, WS-Discovery, WS-Federation, WS-Policy, WS-Security y WS-Trust.

- **Web UI testing** - Comprueba si los elementos visuales de la interfaz de usuario de una aplicación web funcionan correctamente y son fáciles de usar. Es diferente de las pruebas de API, que prueban la comunicación entre los componentes de software.

## Software

-  SoapUI
- [[Domain -  Postman]]