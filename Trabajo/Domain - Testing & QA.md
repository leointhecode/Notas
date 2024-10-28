
**Domain description:**

```
Compilacion 101 de todo lo necesario a saber de las pruebas de software, desde fundamentos, metodologias y automatizacion.
```

**Knowledge Area:**  [[Area - Labor]]


> [!Hello] Index
>1.  [[#Introducción]]
>2. [[#Fundamentos en el proceso de desarrollo de software]]
>3. [[#DevOps y Pruebas]]
>4. [[#Fundamentos del testing]]
>	1. [[#Pruebas vs depuración]]
>	2. [[#¿Porque es importante hacer pruebas?]]
>	3. [[#Error, defecto y fallo]]
>	4. [[#Los siete principios de las pruebas]]
>	5. [[#Artefactos de prueba]]
>	6. [[#Creando casos de prueba]]
>	7. [[#Errores y cómo escribir un informe]]
>	8. [[#Verifique el ciclo de vida de los errores (BLC)]]
>	9. [[#Pruebas funcionales vs pruebas no funcionales]]
>	10. [[#Pruebas de caja negra vs caja blanca]]
>	11. [[#Pruebas Estaticas vs Dinamicas]]
>	12. [[#Pruebas basadas en la experiencia]]
>	13. [[#Técnicas de diseño de pruebas]]
>5. [[#Gestion de las actividades de prueba]]
>6. [[#Herramientas normalmente utilizadas en las pruebas.]]
>7. [[#Agile Testing]]
>8. [[#Automation testing]]
>9. [[#API Testing]]
>10. [[#AI Testing]]
>11. [[#Test lead and management]]


Certifications to achieve: 
 - [x] ISTQB Certified Tester CFLT
 - [ ] ISTQB Certified Agile Tester
 - [ ] ISTQB Test Automation Engineer
 - [ ] ISTQB Test Analyst
 - [ ] ISTQB Test Manager
 - [ ] ISTQB AI testing
 - [ ] ISTQB Security testing
 - [ ] ISTQB Cloud Testing
---

## Introducción

La prueba de software es una disciplina dentro de la ingeniería de software que se realiza a través de una metodología de verificación y validación. Su principal objetivo es el de prevenir la aparición de defectos y si aplica, posteriormente localizar errores en el software para que el equipo de desarrollo los corrija y, de esta manera, mejorar la confiabilidad y el nivel de calidad del sistema.

**Es mejor y más barato encontrar errores en las primeras etapas del desarrollo.**

Habilidades necesarias para ser el mejor tester:

- **Mentalidad lógica**
  - Ser capaz de descomponer un sistema en unidades más pequeñas para crear casos de prueba.
- **Excelente comunicación**
  - Comunicación verbal y escrita para tener el mejor desempeño al comunicar y documentar los errores.
- **Orientado a los detalles**
  - Ser capaz de detectar pequeños errores.
- **Organizado y metódico**
  - Esta es la clave para ejecutar los casos de prueba en un orden determinado y encontrar la mayor cantidad de errores posible.
- **Paciente y persistente**

Algunas responsabilidades clave son:

1. Diseñar un plan de pruebas (¿qué, cuándo y cómo se va a probar?).
2. Definir casos de prueba basados en los requisitos.
3. Gestionar el ambiente y los datos de prueba.
4. Ejecutar casos de prueba.
5. Escribir la documentación de las pruebas finalizadas.
6. Reportar los errores encontrados y hacer seguimiento a su corrección y revalidación.
7. Participar en reuniones diarias de seguimiento y reuniones SCRUM.
8. Redactar informes sobre la calidad del producto.
9. Ayudar a resolver dudas a los analistas de requisitos o POs.
10. Ayudar a los desarrolladores a replicar errores e investigar su solución.
11. Implementar sistemas de QA para prevenir errores en el código fuente.

## Fundamentos en el proceso de desarrollo de software

Para el proceso de desarrollo de software existen diversas metodologías, mediante las cuales y con el uso de diferentes técnicas de testeo, se llevan a cabo las pruebas.

Algunas metodologías son:

- Modelos de desarrollo secuencial 
    - Modelo Cascada, Modelo V

- Modelos de desarrollo iterativo
    - Modelo en espiral, creación de prototipos

- Modelo de desarrollo incremental
    - Proceso unificado

- Métodos de desarrollo y prácticas ágiles 
    - ATDD (Acceptance Testing DrivenDevelopment), BDD (Behavior Driven Development), DDD (Domain Driven Development), FDD (Feature Driven Development), XP (Xtreme Programming), TDD (Test Driven Development)

Dependiendo de la etapa en la que se encuentre el SDLC, se definen el alcance de las pruebas, nivel de detalle de documentación de las pruebas,  las tecnicas de prueba que serán utilizadas y la feasibilidad de la automatizacion para ciertas pruebas. 

**Para cada actividad en el SDLC, existe una actividad de testing correspondiente**

Durante el proceso de desarollo de un producto, tenemos igualmente actividades en el **proceso de revision**, en donde segun la norma ISO/IEC 20246 tenemos las siguientes actividades:

- Planificación 
- Inicio de la revisión 
- Revisión individual
- Comunicación y análisis 
- Reparación e informes

Estas revisiones tienen diferentes roles y responsabilidades,  en donde tenemos: 

**Director**
El director decide que sera revisado y porporciona los recursos necesarios para hacerlo. 

**Autor**
El autor creo el producto de trabajo y  es el encargado de hacer los cambios y modificaciones en el mismo.

**Moderador**
Asegura el funcionamiento efectivo de las reuniones, es responsable de la mediacion y de la gestion del tiempo, de la misma manera, se encarga de mantener un entorno de revisión seguro.

**Escriba**
Recopila anomalias de los revisores y registra la información de la revisión 

**Revisor**
Realiza las revisiones, y puede ser alguien involucrado en el proyecto, un experto en la materia o cualquiera de los interesados.

**Lider de la revisión**
Tiene la responsabilidad general de la revisión,  decide quien participará y organiza cuando y donde se llevará a cabo.

Las revisiones se nos presentan en diferentes tipos, dependiendo del modelo, los requisitos y/o etapa del proyecto, se distinguen...

**Revision informal**
No siguen un proceso definido, no requieren un resultado documentado y su objetivo es detectar anomalías. 

**Revisión guiada**
Es dirigido por el autor, y puede servir para muchos objetivos, normalemente las veremos en updates diarias en sprints

**Revisión técnica** 
Es realizada por técnicos especializados y es dirigida por un moderado, el objetivo es obtener consenso y toma de decisiones.

**Inspeccion**
Es el tipo de revision mas formal, en donde el objetivo principal es encontrar el maximo numero de anomalías,  evalua la calidad y mejora la confianza, se capacita a los autores para mejorar para ello, los autores no pueden actuar como líderes de revisión o escribas.

Para que las revisiones tengan éxito es esencial...

- Definir objetivos claros y criterios de salida medibles
- Elegir el tipo de revisión apropiada
- Realizar las revisiones en trozos pequeños
- Proporcionar retroalimentación a las partes interesadas.
- Proporcionar tiempo suficientes
- Tener apoyo de la gerencia
- Hacer que las revisiones formen parte de la cultura organizacional
- Formación adecuada a los participantes
- Facilitar reuniones.

## DevOps y Pruebas

Gracias a metodologías de CI/CD (continuous integration and continuous development) introducidas por devops, es que tenemos ventajas en el desarrollo como:

- Retroalimentación rápida sobre la calidad del código. 
- La integración continua promueve un enfoque de desplazamiento hacia la izquierda de las pruebas. 
- Promueve procesos automatizados como integración continua y entrega continua, 
- Aumenta la visión sobre las características no funcionales. 
- La automatización a través de un canal (pipeline) de entrega reduce la necesidad de pruebas manuales repetitivas.
- El riesgo en la regresión se minimiza debido a la escala y el rango de las pruebas de regresión automatizadas. 

No obstante, tambien presenta algunos desafíos y riesgos a lo largo del desarrollo...

- El canal de entrega de DevOps debe de estar definido y establecido. 
- Las herramientas de Integración Continua y Entrega Continua deben se ser introducidas y mantenidas.
- La automatización de pruebas requiere recursos adicionales y puede ser difícil de establecer y mantener.

Para mantener un ambiente apropiado es importante que las partes tengan bien implementado su proceso de desplazamiento hacia la izquierda, para ello es importante. 

 - Revisar la especificacion desde la perspectiva de las pruebas.
 - Escribir casos de prueba antes de escribir el codigo.
 - Utilizar CI CD 
 - Completar el analisis estatico del codigo fuente antes de las pruebas dinamicas.
 - Realizar pruebas no funcionales comenzando en el nivel de prueba de componentes.


## Fundamentos del testing

#### Pruebas vs depuración 

Tanto las pruebas como la depuración identifican la causa raiz y condiciones de un defecto en el artefacto, no obstante, la depuración tiene como objetivo final, el corregir el defecto, mientras que las pruebas tienen como unico objetivo, identificarlo. 

Las pruebas van a encontrar mediante pruebas dinámicas y/o estáticas, fallos y defectos en el artefacto, que al ser reportados, posteriormente mediante la depuración, se va a reproducir el fallo, encontrar la causa raiz y finalmente corregirlo.

Posteriormente, se harán pruebas de confirmación comprueban si las correcciones resolvieron el problema. Si las pruebas estáticas detectan un defecto,  no hay necesidad de la reproducción y diagnóstico, ya que no puede haber fallos.

#### ¿Porque es importante hacer pruebas?

Las pruebas son importantes porque ...

- Brindar una mayor calidad de manera indirecta a través de la depuración al identificar los errores, defectos y/o fallos
 - Facilitar la toma de decisiones durante el ciclo de vida de un producto
- Cumplir con requisitos contractuales y/o estándares de la industria 
- ayudan a **reducir** el riesgo de falla durante la operación 
- Pueden ser requeridas por entes regulatorias.
- Contribuyen con el seguimiento y el exito de un proyecto de software. 

Igualmente es importante hacer pruebas de software, debido a que su mala praxis o falta de las mismas puede ocasionar problemas que van desde perdida de dinero o de la reputación, hasta catástrofes y la muerte en casos donde se utilize software durante escenarios críticos. 

Las pruebas pueden contribuir al exito de un proyecto al involucrar a los tester desde etapas tempranas del desarrollo de un producto de software. 

- Al involucrarse con los POs se podra dialogar y ajustar de la manera mas precisa las historias de usuario, y se podrá optimizar tiempo a futuro en el proyecto.
- Al involucrarse con los diseñadores, se podra encargar de que los diseños vayan alineados de manera adecuada con las historias de usuario 
- Al involucrarse con desarrolladores, la implementación del codigo ira de la mano con los criterios de aceptación y validación de las historias de usuario, lo cual tambien ahorrara tiempo y dinero.
- Finalmente al hacer las propias pruebas seguirá contribuyendo al seguimiento y éxito del proyecto de software. 

Dentro de las pruebas, tenemos varios niveles de las mismas.

1. Pruebas de componente (Se prueba un componente o feature en aislamiento i.e *unit testing*)
2. Prueba de integracion de componentes (Se prueba como funciona la interfaz o diferentes componentes de manera simultánea)
3. Pruebas de sistema (Se prueba un sistema completo, es ideal probar elementos no funcionales en este punto)
4. Pruebas de integracion de sistemas (Se encarga de probar aspectos de varios sistemas trabajando en conjunto, ya sean de terceros o no)
5. Prueba de aceptacion (Pruebas hechas a un nivel cliente y/o comercial)

#### Error, defecto y fallo

Si bien el error, el defecto y el fallo estan interrelacionados y los tres forman parte de un problema en el software, son diferentes.

- Un **Error** es una equivocación humana. (Esa equivocación puede generar un defecto)
- Un **Defecto** es una imperfección en un artefacto. 
- Una **Falla** es un comportamiento inesperado del software cuando se produce o se visualiza el defecto en ejecución. 

#### Los siete principios de las pruebas

Estos principios son evaluados en certificaciones de pruebas de software como ISTQB:

1. **Ejecutar pruebas muestra la presencia de defectos, pero NO puede mostrar su ausencia.**
2. **Las pruebas exhaustivas son imposibles.** Lo correcto es realizar un análisis de riesgos y ejecutar los casos de prueba con mayor prioridad.
3. **La calidad asegurada de un sistema debe comenzar lo antes posible.**
4. **La mayoría de los errores relevantes se concentran en grupos específicos de nuestro producto.**
5. **La paradoja del error.** Llega un momento en que el equipo de QA no puede encontrar nuevos errores sin cambiar el plan de pruebas o los casos de prueba.
6. **Las pruebas dependen absolutamente del contexto.**
7. **La falacia de la ausencia de errores.** Más pruebas no aseguran que el software será capaz de funcionar correctamente.

#### Artefactos de prueba

Los artefactos de prueba son productos tangibles del proceso de desarrollo de un producto, en cada etapa del mismo se iran generando diferentes artefactos por parte del equipo de pruebas. 

- **Planeación** - Uno o más planes de prueba.
- **Monitoreo y control** - Diferentes reportes de pruebas y estatus.
- **Análisis** - Definición y Priorización en condiciones de prueba.
- **Diseño** - Casos de prueba 
- **Implementación** - Procedimientos de prueba, suits de prueba 
- **Ejecución** - Resultados de prueba, reportes de defectos y documentación 
- **Finalización** - Resumen de reporte de pruebas.

Es esencial crear entre la base de pruebas y los artefactos (o testware) una trazabilidad en pos de tener un buen monitoreo y control sobre el desarrollo del producto, esta trazabilidad esta basada generalmente afín a los riesgos, es decir, entre más riesgo represente una amenaza tendra un nivel de prioridad más alto al momento de testear.

Igualmente, una buena trazabilidad nos dará una mejor visión y entendimiento del impacto de los cambios y el progreso de las pruebas, va a facilitar las auditorias de prueba y va a ayudar a cumplir con los criterios de gobierno de TI.

#### Creando casos de prueba

Recuerde que los casos de prueba se basan en los requisitos del cliente y de BA. Usando las pautas que fueron comunicadas por el lado de requisitos, tenemos que reconocer **Cómo** se realizará la prueba, **Qué** esperamos **Para** qué estamos probando esto.

Tenga en cuenta que siempre tenemos que fotografiar pruebas de las pruebas o casos fallidos.

#### Errores y cómo escribir un informe

Lo primero es lo primero, en términos informáticos un bug es un error o defecto en el software que hace que un programa no funcione correctamente.

La mayoría de los errores se crean debido a errores de quienes desarrollan el código del software, al diseñarlo o cuando no son compatibles con otras aplicaciones o hardware. 

Una vez que ya tenemos la idea de qué es un error, podemos entender la importancia de reportarlos, y aún más, la importancia de reportarlos correctamente para poder solucionarlos de la manera más rápida posible, si teniendo esto en cuenta queremos se puede decir que...

*La solución de una falla depende de la eficiencia con la que se reporta*

Un informe de error sigue una estructura similar (tenga en cuenta que algunos campos pueden ser necesarios o no según las necesidades del equipo de desarrollo).

- ID de error
- Título del error
- ¿Quién está informando?
- Descripción del error
- Pasos de reproducción
- Resultado Esperado
- Resultado obtenido
- Evidencia de error
- Entorno donde sucedió (navegador, sistema operativo)
- Severidad / Prioridad 

Te recomendamos encarecidamente esto:

- Trate de evitar palabras negativas como (El navegador no, no puede, etc.)
- Utilizar siempre los verbos en presente.
- Mantenga su explicación lo más simple posible.

#### Verifique el ciclo de vida de los errores (BLC)

- Error encontrado 
- El error tiene un estado Activo
- El error está asignado a un desarrollador.
- El error está marcado como asignado.
- El desarrollador comprueba el error.
	- NaB (No es un error)
	- Fijado 
- Si se soluciona, el error se marca como verificar
	 - El error se marca como asignado si el error no se ha resuelto
	 - El error está marcado como cerrado.

#### Pruebas funcionales vs pruebas no funcionales

Las pruebas se pueden clasificar en dos grandes grupos, las pruebas funcionales (pruebas que se basan en los requisitos y consultas del cliente y de los BA) y las pruebas no funcionales (algunas características como confiabilidad, seguridad, capacidad y compatibilidad dependen de pruebas no funcionales).

Pruebas funcionales

- **Pruebas unitarias** (pequeñas pruebas en una etapa de desarrollo, generalmente están automatizadas)
- **Prueba de humo** (Se ejecuta después del lanzamiento de una nueva compilación y se crea para garantizar que ciertas funcionalidades básicas y críticas funcionen correctamente)
- **Pruebas de integración** (Especialmente realizadas con proyectos grandes, probamos una interfaz integrada de varios componentes)
- **Prueba de regresión** (Prueba un sistema que fue probado previamente para verificar que no tengamos nuevos errores innit, normalmente se hace al final de un sprint)
- **Prueba de aceptación** (Prueba de usuario, última prueba antes del envío realizada por una tercera persona)

Pruebas no funcionales

- **Pruebas de rendimiento** (Prueba la estabilidad, velocidad, escalabilidad y capacidad de respuesta)
	- **Pruebas de estrés**
	- **Prueba de carga**
	- **Prueba de carga**
	- **Prueba de picos**
- **Pruebas de seguridad** (pentesting, etc.)

### Pruebas de caja negra vs caja blanca

Recordemos que las técnicas de caja negra, se enfocan principalmente en la parte funcional de la aplicación, no en el proceso interior, por lo cual,  consideramos únicamente el input y el output.

Por otra parte, las pruebas de caja blanca toman en cuenta la implementacion del software, las podemos usar de manera estatica o dinamica.

Realizar solamente pruebas de una sola caja, no representan una cobertura total, se deben utilizar en conjunto, agregando unas tecnicas mas, para poder aumentar la confianza que tenemos en el codigo.

#### Pruebas Estaticas vs Dinamicas

Durante las pruebas estaticas no se ejecuta el software, se evalua con revision y herramientas de analisis estatico como debuggers, en general podemos notar que mejoran la calidad, detectan defectos, algunos productos de trabajo que son evaluables por pruebas estaticos son ...

- Especificacion de requisitos
- Codigo fuente
- Planes de prueba
- Casos de prueba
- Documentacion

El valor de las pruebas estaticas brilla en particular en las pruebas tempranas, tambien nos puede identificar defectos particulares y nos generan confianza en los productos de trabajo.

Una de las diferencias con respecto a las pruebas dinamicas es que simplemente encuentran defectos diferentes, las pruebas estaticas encuentran defectos directamente, mientras que las dinamicas detectan fallos, las pruebas dinamicas no se pueden utilizar en productos de trabajo no ejecutables.

#### Pruebas basadas en la experiencia

Las pruebas basadas en la experiencia suelen tener un impacto mas grande conforme al seniority del tester, como su nombre lo dice, suelen ser pruebas mas flexibles en donde tiene una injerencia importante el conocimiento que tiene el tester sobre la aplicación,  sus versiones pasadas, fallos en aplicaciones similares, errores que suelen cometer los desarrolladores en tales lares de la industria.

### Técnicas de diseño de pruebas

**Particion de equivalencia**
- Una prueba por cada particion es suficiente. 
- Se pueden identificar para cualquier elemento de datos del objeto de prueba
- Existen particiones validas e invalidas.

**Analisis de valor limite**
- Valida los limites de las particiones de equivalencia
- Valores limite = minimo y maximo de una particion
- BVA (Boundary Value Analysis) de 2 valores
- BVA de 3 valores

**Tablas de decision**
- Son muy utiles para reglas de negocio compleja
- Definen condiciones y acciones resultantes
- Notacion condiciones: T = verdadero, F = falso
- Cada columna de la tabla representa un caso de prueba

**Transicion de estados**
- Diagrama de transicion de estados
- Caso de prueba = Secuencia de eventos y cambios de estados
- Cobertuta de todos los estados
- Cobertura de transiciones validas.
- Cobertura de todas las transiciones

**Pruebas de sentencia y cobertura**
- Cobertura = sentencias ejecutadas / total de sentencias ejecutadas
- Se expresa en porcentaje
- 100% cobertura indica que cada sentencia se ha ejecutado al menos 1 vez
- importante seleccionar las sentencias adecuadas 

**Pruebas de rama y cobertura**
- Un resultado de decision
- Cobertura = ramas probadas / total de ramas
- Se expresa como un porcentasje
- Cobertura rama > Cobertura sentencia

**Prediccion de errores**
-  Requiere conocer como funcionó la aplicación en el pasado
- Conocer los tipos de errores que los desarrolladores tienden a cometer
- Los tipos de fallas que se han producido en otras aplicaciones similares

**Pruebas exploratorias**
- Mejor conocido como ad-hoc testing
- Se utilizan para aprender mas sobre el objeto bajo prueba
- A veces utilizan un enfoque basado en sesiones
- Son utiles cuando hay poca o inadecuada documentación 
- Cuando hay presion de tiempo

**Pruebas basadas en listas de comprobacion**
- Los elementos de la lista a menudo se formulan como pregunta
- Se vuelven menos efectivas con el tiempo
- Pueden proporcionar pautas y cierto grado de consistencia a las pruebas

## Gestion de las actividades de prueba

**Proposito y contenido de un plan de prueba**

Un plan de prueba documenta los medios y el cronograma para lograr los objetivos de prueba, tambien ayuda a garantizar que las actividades de prueba realizadas cu,plan con los criterios establecidos. 

Sirven como medio de comunicacion con los miembros del equipo y otras partes interesadas, finalmente demuestran que las pruebas se adheriran a la politica de pruebas y la estrategia de pruebas existentes (o explica porque la prueba se desviara de ellas)

Tipicamente su contenido es de:
- Contexto de las pruebas
- Supuestos y limitaciones de proyecto
- Partes interesadas
- Comunicación 
- Registro de riesgos
- Enfoque de prueba
- Presupuesto y cronograma 

Entre cada prueba y plan tenemos criterios de entrada y de salida, que se pueden reinterpretar como acciones previas y criterios de finalización. 

**Tecnicas de estimacion**

Utilizamos tecnicas de estimacion para poder calcular el esfuerzo requerido dentro de un plan de pruebas, esto es parte de la planificacion ya sea de la iteracion o de la entrega

- Estimacion basada en proporciones (Estimacion basada en cantidad de pruebas a resolver)
- Extrapolacion (Estimacion mediante el uso de modelos matematicos)
- delphi de banda ancha (Estimacion por expertos y consenso)
- Estimacion de 3 puntos (Estimacion por expertos basados entre el mejor caso, el peor caso, el mas probable y un promedio de esas 3)


**Priorizacion de casos de prueba**

Durante una entrega o iteracion, es posible que diversos casos de prueba deban ser priorizados debido a limitantes (i.e presupuesto o tiempo), estas priorizaciones pueden ser:

- Priorización basada en el riesgo (Probabilidad de que ocurra e impacto)
- Priorizacion basada en la cobertura
- Priorización basada en requisitos


## Herramientas normalmente utilizadas en las pruebas.

Para evidencia:
- Disparo de luz (fotos)
- Screencastify (vídeos)
- BrowserStack (pruebas entre navegadores)

Manejo de Proyecto SCRUM / Errores:
- Jira
- Azure DevOps
- Trello
- Excel/Word

Manejar casos de prueba
- Testrail
- TestLink
- TestLodge
- Enlace de prueba
- Planes de prueba de Azure
- MSExcel
- MS Word

Pruebas de automatización y pruebas de API.
- Selenium
- Node JS
- cypress
- TestCafe
- SOAPUI
- Postman
- Jenkins
- Bamboo

## Agile Testing 

> [!NOTE] This is a specialization
> - [[Domain -  Agile]]

## Automation testing

> [!NOTE] This is a specialization
> - [[Domain -  Automatización]]

## API Testing

> [!NOTE] This is a specialization
> - [[Domain -  APIs]]


## AI Testing


## Test lead and management


> [!NOTE] This is a specialization
> - [[Domain -  Manejo de Proyecto]]

