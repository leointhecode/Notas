
**Domain description:**

```

```

**Knowledge Area:** [[Domain -  Automatización]]


> [!NOTE] Index
> 1. [[#Introducción y ventajas]]

## Introducción y ventajas

Robot Framework es un framework open source de automatización para "acceptance testing", esto debido a que sigue diversas metodologias como: 

- Keyword-driven
- Behavior-driven
- Data-driven

Robot tiene una sintactica simple y sus capacidades pueden ser extendidas con librerias en Python o Java.

Es exclusivo para Web Automation, API automation, RPA (Robotic Process Automation) y Database Testing.

## Instalar y Configurar 

Asegurate de instalar Python en el OS y revisa que este disponible en el path de instalacion, y en el caso que sea necesario, crea un venv de python e instala los siguientes paquetes.

1. Instala Robot Framework

```Python
pip install robotframework
```

2. Instala la libreria de Selenium

```Python
pip install --upgrade robotframework-seleniumlibrary
```

3. Recomendamos *Hyper Robot Framework Support* como highlight plugin en IDE

4. Crea tu primer archivo de test con extension .robot

```bash
nvim testDemo1.robot
```

5. Crea tu primer caso de prueba!

```robot
#Robot utiliza el simbolo * para crear casos de prueba
*** Settings *** 

#Las keyword disponibles para settings se agregan aqui dejando un tab de espacio para variables

Documentation    To validate login form
Library    SeleniumLibrary

*** Test Cases ***
Validate Succesful Login #Nombre del Test case
	open the browser payment url #Steps para el caso de prueba
	fill the login form
	wait until checks display failure
	verify message

*** Keywords ***
open the browser payment url

```


## Tests con Keywords y Variables

## Selenium Automatizacion Funcional

## DDT y Parametrizacion en Selenium

## Crear Keywords Personalizadas

## Implementar POM para Organizar Tests

## Ejecucion de Tests en Paralelo y Reportes

## Tags, Filtros y CI/CD Jenkins

## API Testing con Robot