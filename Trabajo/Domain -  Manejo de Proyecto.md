
**Domain description:**

```

```

**Knowledge Area:** [[Domain - Testing & QA]]


> [!NOTE] Index
> 1. [[#Introducción]]
> 2. [[#Etapas en un proyecto de QA]]
> 3. [[#Algunos Errores Comunes a Evitar]]
> 4. [[#Testeo Temprano]]
> 5. [[#Las historias de usuario]]
>     1. [[#Importancia de las Historias de Usuario]] 
>     2. [[#Proceso de Conversión de Historias de Usuario a Casos de Prueba]]
> 6. [[#Como definir una estrategia de pruebas]]
>     1. [[#Piramide de automatizacion]]
>     2. [[#Cómo crear un plan de pruebas funcional]]

## Introducción 

La gestión de los casos de prueba son parte del proceso en el desarrollo de software. Implica la creación, organización y ejecución de una serie de diferentes pruebas diseñadas para verificar que el software funcione como debería.

## Etapas en un proyecto de QA

Como lead en QA te vas a desempeñar en estas etapas:

1. **Planificación** 
Durante la etapa de planificación vamos a identificar los requisitos funcionales y los no funcionales,  diseñaremos la estrategia de pruebas, en donde se define el alcance de las pruebas, los tipos de pruebas a realizar y los recursos necesarios, finalmente se detallan en un cronograma de pruebas, los responsables y los criterios de aceptación. 

2. **Creación de casos de prueba** 
Durante esta etapa se escriben los casos de prueba individuales, siguiendo la norma sl escrbir un TC, igualmente vamos a organizar los casos de prueba en suits según diferentes criterios. 

3. Ejecución de pruebas
Antes de la ejecución nos tenemos que asegurar de preparar el ambiente de pruebas con los datos necesarios, posteriormente se ejecutarán uno por uno y se documentan los resultados de la prueba, incluyendo cualquier error.

4. Análisis de resultados
Se analizan los resultados de las pruebas para identificar defectos y asignarles una severidad y prioridad, se generan informes detallados siguiedo ls norma para mandarlo con los desarrolladores. 

5. Cierre de pruebas
Se verifica que los defectos hayan sido corregidos, se evalua sinse alcanzo el criterio esperado y de elabora un informe final que compila los resultados obtenidos en el testeo. 

Cómo Ser un Excelente Líder de Pruebas

El líder de pruebas, o líder de control de calidad (QA), es la persona encargada de diseñar el plan de pruebas, el ritmo del proyecto de control de calidad y asume responsabilidades adicionales por los demás miembros del equipo de control de calidad.

**Las responsabilidades comunes del líder de control de calidad son:**

- Diseñar el plan de pruebas y liderar la estrategia de automatización.
- Guiar al equipo para que integre la calidad en todas las fases del ciclo de vida del desarrollo de software (SDLC).
- Brindar asistencia técnica a otros testers que trabajan en el mismo producto.
- Ser un mentor de otros testers dentro del mismo equipo.
- Realizar revisiones por pares de los casos de prueba de otros testers.
- Apoyar en la clasificación de los errores encontrados en el sprint.
- Coordinar las pruebas de aceptación del usuario (UAT) con los usuarios finales.
- Ejecutar pruebas, reportar errores y trabajar en estrecha colaboración con los desarrolladores y todos los testers.
- Revisar el código de prueba y aprobar las solicitudes de incorporación (pull requests).
- Ayudar con las entrevistas técnicas de otros testers.
- Revisar el proceso de prueba y las métricas de calidad.

## Algunos Errores Comunes a Evitar

Como líder de control de calidad, es tu responsabilidad evitar estos errores en tu equipo ágil:

- Las pruebas se dejan para el último minuto en el sprint.
- Las pruebas son solo para los testers del equipo.
- Existe un equipo de pruebas separado de los desarrolladores.
- Desarrollar en el primer sprint y probar en el segundo.
- Testers que trabajan en varios equipos en paralelo.
- Testers esperando a que los programadores terminen de configurar la historia.
- Testers que piensan que son los guardianes de la calidad y no dejan que nadie los ayude.
- Testers que cambian de equipo durante un sprint.

## Testeo Temprano

**Pruebas Estáticas**

Las pruebas estáticas no requieren la ejecución de software para llevarse a cabo. Su objetivo es la prevención temprana y la detección de errores.

Por ejemplo:

- Revisión del historial
- Criterios de Aceptación
- Planes de prueba

**Pruebas Dinámicas**

Las pruebas dinámicas se ejecutan mientras el código se está ejecutando. Su objetivo es asegurar que el software se comporte de acuerdo a sus requisitos.

Por ejemplo:

- Revisión de aspectos funcionales y no funcionales de la aplicación

## Las historias de usuario

**Definición**:
Las historias de usuario son descripciones simples y breves de una funcionalidad o característica deseada del sistema desde la perspectiva del usuario final. Se utilizan en metodologías ágiles para capturar los requisitos del software de una manera que sea fácil de entender para todos los involucrados.

### Importancia de las Historias de Usuario

1. **Enfoque en el Usuario**:
   - Las historias de usuario aseguran que el equipo de desarrollo se centre en las necesidades y expectativas del usuario final.
   
2. **Comunicación Clara**:
   - Facilitan la comunicación entre los desarrolladores, los testers, los stakeholders y los usuarios finales, asegurando que todos entiendan los requisitos de manera uniforme.

3. **Flexibilidad y Adaptación**:
   - Permiten cambios y ajustes rápidos, adaptándose fácilmente a nuevas necesidades o requisitos durante el ciclo de desarrollo.

4. **Priorización y Planificación**:
   - Ayudan a priorizar las tareas en función del valor que aportan al usuario, permitiendo una planificación más eficiente del trabajo.

### Proceso de Conversión de Historias de Usuario a Casos de Prueba

**1. Comprensión de la Historia de Usuario**:
   - **Revisión Inicial**: El equipo de QA debe revisar la historia de usuario para entender completamente la funcionalidad y el beneficio esperado.
   - **Preguntas y Clarificaciones**: Si hay aspectos ambiguos o poco claros, es crucial hacer preguntas a los Product Owners o stakeholders para obtener clarificaciones.

**2. Identificación de Criterios de Aceptación**:
   - Los criterios de aceptación definen las condiciones que la historia de usuario debe cumplir para ser considerada completa. 
   - Estos criterios se convierten en la base de los casos de prueba.
   - Ejemplo de criterios de aceptación para la historia de usuario anterior:
     - El filtro debe permitir seleccionar una o varias categorías.
     - Los productos mostrados deben actualizarse instantáneamente al aplicar el filtro.
     - El filtro debe ser fácil de restablecer para mostrar todos los productos nuevamente.

**3. Creación de Casos de Prueba**:
   - **Desglose de Funcionalidades**: Divide la funcionalidad de la historia de usuario en componentes manejables.
   - **Definición de Escenarios de Prueba**: Basado en los criterios de aceptación, define diferentes escenarios que cubran todas las posibles variaciones y condiciones.
     - Ejemplo de escenarios de prueba:
       1. Filtrar por una sola categoría.
       2. Filtrar por múltiples categorías.
       3. Restablecer el filtro para ver todos los productos.
   - **Documentación Detallada**: Escribe los casos de prueba de manera clara y detallada, incluyendo pasos específicos, datos de prueba, y resultados esperados.
     - Ejemplo de un caso de prueba:
       - **Título**: Filtrar productos por una sola categoría.
       - **Pasos**:
         1. Navegar a la página de productos.
         2. Seleccionar una categoría del filtro.
       - **Resultado Esperado**: Solo los productos de la categoría seleccionada se muestran.

**4. Revisión y Validación**:
   - **Revisión Interna**: Los casos de prueba deben ser revisados por otros miembros del equipo de QA para asegurar la cobertura completa y la precisión.
   - **Validación con Product Owners**: Validar los casos de prueba con los Product Owners para asegurar que cubren todos los aspectos importantes de la historia de usuario.

**5. Ejecución de Casos de Prueba**:
   - **Preparación del Ambiente de Pruebas**: Asegurarse de que el ambiente de pruebas esté listo y los datos de prueba estén disponibles.
   - **Ejecución y Registro de Resultados**: Ejecutar los casos de prueba y registrar los resultados, documentando cualquier discrepancia o defecto encontrado.
   - **Reporte de Defectos**: Reportar y gestionar cualquier defecto encontrado durante la ejecución de las pruebas.

**Estrategia INVEST**

La estrategia INVEST se refiere a:

- **I**ndependiente (Las historias se pueden implementar en cualquier orden)
- **N**egociable (Alcanzar el objetivo sin sugerir una implementación específica)
- **V**alioso (Algo que el usuario puede usar, no solo una tarea técnica)
- **E**stimable (No requiere mayor investigación)
- **S**e dividen en partes pequeñas (Puede pasar del concepto a la implementación en poco tiempo)
- **T**esteadas (Son medibles para verificar que la historia esté completada)

**Estrategia BDD**

Tiene como significado (*Behavior Driven Development*), es decir, desarollo enfocado en el comoprtamiento, es decir, definimos escenarios basandonos en el comportamiento del usuario.

El principal objetivo es equipo describa los detalles de como se debe comportar la aplicacion a desarrollar, y de esta forma sera comprensible por todos.

**Aplicando BDD**

La metodologia BDD, se aplica cuando estamos escribiendo las historias de usuario (que vienen siendo los comportamientos esperados del usuario), y tienen como proposito, normalizar, simplificar y globalizar tales comportamientos para una comunicacion optima.

```
GIVEN soy un usuario de la tienda online logueado
WHEN Estoy en la agina de un producto
THEN Debo ver la opcion para agregarlo a mi lista de deseos
```


## Como definir una estrategia de pruebas

Una estrategia de pruebas es un conjunto de definiciones de alto nivel que nos van a determinar como vamos a llevar el proceso de pruebas del equipo, esto va a influenciar en las desiciones del equipo y en el como se van a invertir los esfuerzos.

- Se debe de estar revisando frecuentemente
- EL codigo que se sube SIEMPRE debe de ser de alta calidad

**Dentro de la sprint:**

0. Antes del sprint tenemos el early testing, refinamiento de historias, el BDD y pruebas estaticas
1. Al iniciar la sprint, iniciamos el desarrollo y pruebas de manera paralela, (El lider de pruebas debe revisar con atencion las pruebas unitarias implementadas y se debe de tener una comunicacion cercana con el equipo de desarrollo), tenemos analisis estatico del codigo (CodeQL, SonnarQ), aprobacion de pull requests, creacion del test data y se prepara el ambiente de testeo.
2. De la etapa anterior a la actual, se despliegan los cambios a un ambiente de pruebas y se iterara en varias ocasiones ... smoke testing, ad hoc testing, pruebas basadas en requisitos, API testing, Test automation UI, Bug fixes, retesting, regression, integration y DoD checklist. TODO EL EQUIPO (NO SOLO QA) ESTA PROBANDO
3. Posterior al loop anterior, se hace un despliegue a pre-produccion, se hacen pruebas de performance, seguridad y se hace nuevamente la sprint review con el cliente y ahi mismo se puede hacer la pruba de aceptacion
4. Despliegue a produccion, se haces pruebas post go live y monitoreo

La estrategia de pruebas anterior, se le conoce como **enfoque shift left**.


### Piramide de automatizacion

La base de la piramide esta conformada por las pruebas unitarias, podemos devenir muchos errores a traves de esto, y se utilizan herramientas como junit o TestNG

Seguido en el nivel medio se hace API test o service testing, esto para asegurarnos que la comunicacion entre componentes esta funcionando, se utilizan herramientas como Automated, Soap UI o Rest client.

Seguido, tenemos las GUI Test, con el objetivo de que las expectativas del cliente sean alcanzadas, se utiliza automatizacion como Cucumber, Selenium, Behave

FInalmente se hace Manual test.

Esta piramide, muestra la velocidad de ejecucion (mas rapidas de la base a la punta), el costo del testeo (mas barato de la base a la punta) y la abundacia que deberiamos tener de esas pruebas (mas pruebas de la base a la punta)

### Cómo crear un plan de pruebas funcional

Un plan de pruebas define la estrategia para las pruebas y guía al equipo sobre cómo probar la aplicación. Define el Qué, Cómo, Dónde y Quién.

Dependiendo de la complejidad del proyecto, generalmente para sprints cortos y con un objetivo de sprint bien definido, un plan de pruebas ágil o lite es más que suficiente.

La estructura básica de un plan de pruebas incluiría:

- **Plan de pruebas ágil** (Descripción del proyecto y el objetivo del plan).
- **Alcance de las pruebas** (Qué vamos a probar y qué está fuera de alcance).
- **Tipos de pruebas o estrategias** (Cómo vamos a ejecutar las pruebas y en qué condiciones).
- **Ambiente de pruebas** (El lugar y las circunstancias donde se realizarán las pruebas).
- **Datos de prueba** (Los datos que se usarán como casos de prueba, detallados con precisión).
- **Plan de riesgos** (Los posibles riesgos que pueden afectar las pruebas, la severidad del riesgo y una recomendación sobre cómo mitigarlo).

Estos elementos aseguran que el equipo de pruebas tenga una guía clara y estructurada para realizar pruebas efectivas durante el ciclo de desarrollo del software.

