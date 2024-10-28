
**Domain description:**

```
Este dominio toma en consideración las principales ramas de automatización utilizadas ampliamente en QA
```

**Knowledge Area:**  [[Domain - Testing & QA]]


> [!NOTE] Index
> 1. [[#Pruebas Manuales vs Pruebas Automatizadas]]
> 	1. [[#Pruebas Manuales]]
> 	2. [[#Pruebas Automatizadas]]
> 	
> 2. [[#Frameworks de automatización de UI]]
> 	1. [[#Selenium]]
> 	2. [[#Cypress]]
> 3. [[#Frameworks de automatización de pruebas]]
> 	1. [[#Pytest]] 
> 


## Pruebas Manuales vs Pruebas Automatizadas 
### Pruebas Manuales

Ejecutadas directamente por los testers (especialistas en pruebas de software), simulan las acciones del usuario final.

*Ventajas*
- Son más rápidas para proyectos cortos.
- Más flexibles.
- Debido a la ejecución humana, podemos detectar defectos no funcionales durante las pruebas.
- No se requieren conocimientos técnicos.
- Podemos probar escenarios complejos con pasos de reproducción largos en sistemas antiguos o heredados.

*Desventajas*
- Actividad repetitiva y tediosa.
- Si la base de datos de defectos es grande, la nueva prueba del sistema puede resultar costosa de ejecutar.
- En proyectos grandes, la repetición puede hacer que el equipo de control de calidad omita errores debido al cansancio humano.

### Pruebas Automatizadas

Pruebas codificadas mediante scripts y programas. Simulan las acciones del usuario final. Las pruebas se ejecutan automáticamente en un servidor de pruebas, laptop o un sistema de integración CI/CD (como Jenkins o Bamboo).

*Ventajas*
- La ejecución del caso de prueba es rápida y eficiente.
- Se obtiene un alto nivel de confianza y precisión.
- Tienen un ROI (Retorno de la inversión) más alto en proyectos grandes.
- Son reutilizables y se pueden volver a probar continuamente.
- Las pruebas se pueden programar para que se ejecuten sin intervención humana, mediante CI/CD.

*Desventajas*
- La automatización requiere una inversión de tiempo.
- Se requieren conocimientos técnicos.
- Algunas herramientas de automatización son costosas.
- No brindan información sobre ciertos aspectos del sistema, como la usabilidad.

## Frameworks de automatización de UI

Los frameworks de automatización para *user interfaces* te permiten crear scripts que simulan las acciones de un usuario real, como hacer clic en botones, ingresar texto y navegar por diferentes páginas.

### Selenium 

> [!NOTE] This is a specialization
> - [[Domain - Selenium]]

### Cypress
Cypress es un framework de código abierto para la automatización de pruebas de front-end, especialmente diseñado para aplicaciones web modernas. A diferencia de otras herramientas de automatización, Cypress se ejecuta dentro del mismo navegador que la aplicación que se está probando, lo que lo hace más rápido y confiable.
