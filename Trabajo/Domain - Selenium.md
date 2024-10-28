
**Project description:**

```

```

**Knowledge Area:** [[Domain -  Automatización]]

> [!NOTE] Index
>  1. [[#Conceptos Básicos]]
>  2. [[#Localizadores]]
>  3.  [[#Localizadores Relativos]]
>  4. [[#Aserciones]]
>  5. [[#Autenticación Básica]]
>  6. [[#Selenium Grid]]
>  7. [[#Selenium IDE]]
>  8. [[#Send KEYS]]
>  9. [[#Navegación]]
>  10. [[#Errores Comunes]]
>  11. [[#Pruebas de Geolocalización con BiDirectional API/CDP]]
>  12. [[#Pruebas Responsivas con BiDirectional API/CDP]]
>  13. 

### Conceptos Básicos

En Selenium para Python, no es necesario tener un navegador específico instalado para realizar pruebas. Simplemente se requiere ejecutar el driver correspondiente. Por ejemplo:

```Python
from selenium import webdriver

#Ir al navegador
driver = webdriver.Chrome()
```

En este ejemplo, el sistema operativo en ejecución no tiene instalado el navegador Chrome o basado en Chromium.

## Localizadores

Los localizadores son la forma en que Selenium interactúa con los servicios web de prueba. [Aquí](https://www.selenium.dev/documentation/webdriver/elements/locators/) puedes encontrar la documentación.

- El localizador por ID es el mejor localizador para usar si está disponible.
- Para construir localizadores PATH, queremos usar `//etiqueta[@atributo='valor']`.

Los selectores, en pocas palabras, son cómo podemos identificar un elemento sin afectar a los demás elementos.

Algunos plugins recomendados son:
- CSS and XPath checker
- Relative XPath helper
- TruePath

**ID**
El selector de CSS por ID se utiliza con el símbolo de gato (#).

Si tuviéramos un ID para un objeto dado id="username", se utilizaría un selector del estilo "#username". En el caso de que el objeto fuera un input, podemos fortalecer este mediante su suma del estilo, esto lo podemos extender a los tipos de elementos que encontramos en HTML:

- "input#username"
- "textarea.myclass"
- "div.myclass2"

**Atributos**
Se pueden localizar objetos por tipos, por ejemplo, en un objeto `type="email`.
El localizador sería: `[type='email']`.

**ID y Atributos**
Los selectores se pueden mezclar entre ellos, por ejemplo:

`input#username[type='text']`

Notemos que en el ejemplo anterior estamos localizando por ID, tipo y atributo simultáneamente.

**XPath**

En XPath se sigue una nomenclatura diferente a la de los demás localizadores, por ejemplo:

`//button[@id='submit']`

- Siempre partimos con una doble diagonal.
- Proporcionamos el tipo de objeto buscado.
- Se agrega el `@`.
- Finalmente, se adiciona un atributo.

**XPath or and**

`//button[@id='submit' or @type='text']`

En este ejemplo estamos dando dos opciones para encontrar un elemento; en este caso particular, si el elemento tiene id *submit* o type *text* nos lo devolverá.

`//button[@id='submit' and @type='text']`

Para este segundo caso, estamos adicionando una condición más para encontrar; al contrario del ejemplo anterior, se deben de cumplir ambas sentencias para poder seleccionar el elemento.

**XPath con Texto**

`//div[text()='Text Box']`

A veces tendremos situaciones en las que no haya ningún elemento de fácil acceso que nos permita localizar un objeto; para ello, podemos utilizar el método visto para encontrar un elemento con cierto texto.

Si solamente tenemos parte del texto de un elemento y no tenemos todo, podemos usar la función `contains`.

`//span[contains(text(),'Links')]`

En este caso nos devolvería todos los elementos que cumplan los requisitos base y que además tengan la palabra "Links" dentro de ellos.

Un ejemplo más complejo:

`//div[contains(text(),'$') and contains(@class,'gray')]`

## Localizadores Relativos

Los localizadores relativos son un conjunto de estrategias para localizar elementos en relación con otros elementos en la página web. Esta función proporciona más flexibilidad y legibilidad al escribir pruebas automatizadas, ya que permite a los testers expresar localizadores de elementos en relación con elementos cercanos en lugar de depender únicamente de localizadores absolutos como IDs o selectores CSS.

Hay cinco tipos de localizadores relativos en Selenium 4:

1. **above**: Esta estrategia localiza un elemento que está posicionado por encima de un elemento de referencia.
2. **below**: Esta estrategia localiza un elemento que está posicionado por debajo de un elemento de referencia.
3. **toLeftOf**: Esta estrategia localiza un elemento que está posicionado a la izquierda de un elemento de referencia.
4. **toRightOf**: Esta estrategia localiza un elemento que está posicionado a la derecha de un elemento de referencia.
5. **near**: Esta estrategia localiza un elemento que está posicionado cerca de un elemento de referencia, en cualquier dirección.

Aquí tienes un ejemplo de cómo podrías usar localizadores relativos en Selenium:

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.locators.RelativeLocator;

public class Selenium4RelativeLocatorsExample {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.example.com");

        WebElement usernameField = driver.findElement(By.id("username"));
        WebElement passwordField = driver.findElement(By.id("password"));
        WebElement loginButton = driver.findElement(RelativeLocator.withTagName("button").toRightOf(usernameField).below(passwordField));
        
        // Ahora puedes interactuar con el botón de inicio de sesión
        
        // Cerrar el navegador
        driver.quit();
    }
}
```

En este ejemplo, estamos localizando el botón de inicio de sesión en un formulario de inicio de sesión usando localizadores relativos. Encontramos el campo de nombre de usuario por su ID, encontramos el campo de contraseña por su ID y luego usamos localizadores relativos para localizar el botón de inicio de sesión en relación con estos campos. Esto hace que el código sea más legible y comprensible, ya que expresa claramente la relación entre los elementos involucrados.

## Aserciones

Una aserción es básicamente una condición `if` que sigue esta estructura:
```python
assert objeto_a_comparar == "condición"
```

Como es habitual, el operador `==` no es obligatorio, ya que se puede hacer uso de cualquier operador de comparación que exista, como `not`, `<`, `is_displayed()`, etc.

## Autenticación Básica

La autenticación básica es una función que permite automatizar la prueba de aplicaciones web que requieren autenticación HTTP básica.

Para manejar la autenticación básica en Selenium 4, puedes usar la interfaz `WebDriver.Options` para establecer las credenciales antes de navegar a la página protegida. Aquí tienes un ejemplo de cómo hacerlo en Java:

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;

public class BasicAuthenticationExample {
    public static void main(String[] args) {
        // Configurar opciones de Chrome con credenciales
        ChromeOptions options = new ChromeOptions();
        options.addArguments("--disable-popup-blocking");
        options.addArguments("--disable-notifications");
        options.addArguments("--disable-extensions");
        options.addArguments("--no-sandbox");
        options.addArguments("--disable-infobars");
        options.addArguments("--disable-dev-shm-usage");
        options.addArguments("--headless");
        options.addArguments("--window-size=1920,1080");
        options.addArguments("--disable-gpu");
        options.addArguments("--disable-features=VizDisplayCompositor");

        // Establecer nombre de usuario y contraseña para la autenticación básica
        options.addArguments("--user=tu_usuario");
        options.addArguments("--password=tu_contraseña");

        // Crear instancia de WebDriver
        WebDriver driver = new ChromeDriver(options);

        // Navegar a la URL protegida por autenticación básica
        driver.get("https://tu_usuario:tu_contraseña@example.com");

        // Realizar más acciones en la página protegida

        // Cerrar el navegador
        driver.quit();
    }
}
```

En este ejemplo:

1. Configuramos las opciones de Chrome usando `ChromeOptions` para configurar la instancia del WebDriver de Chrome.
2. Deshabilitamos ciertas características del navegador y configuramos el tamaño de la ventana para el modo sin cabeza.
3. Especificamos el nombre de usuario y la contraseña para la autenticación básica usando los argumentos `--user` y `--password`.
4. Creamos una nueva instancia de `ChromeDriver` con las opciones configuradas.
5. Navegamos a la URL protegida por autenticación básica, incluyendo las credenciales en la URL misma.
6. Realizamos más acciones en la página protegida según sea necesario.
7. Finalmente, cerramos la instancia del WebDriver para cerrar el navegador.


## Selenium Grid

Selenium Grid es una herramienta utilizada para ejecutar múltiples pruebas simultáneamente en diferentes máquinas y navegadores en un entorno de pruebas distribuido. Permite ejecutar pruebas en paralelo, lo que aumenta la eficiencia y reduce el tiempo total de ejecución de pruebas.

En general, Selenium Grid sigue siendo un componente crucial para lograr una automatización de pruebas eficiente y escalable en Selenium 4, especialmente en escenarios donde se necesita ejecutar pruebas en múltiples navegadores, dispositivos y entornos.

## Selenium IDE

Selenium IDE (Entorno de Desarrollo Integrado) es una herramienta de grabación y reproducción para crear scripts de prueba automatizados sin escribir código. Proporciona una interfaz fácil de usar para grabar interacciones de usuario con una aplicación web y generar código de Selenium WebDriver.

Tiene una herramienta útil llamada *Record play*, donde básicamente puedes:
- Iniciar el IDE.
- Ir al sitio web adecuado.
- Presionar grabar.
- Finalizar la prueba.
- Asignar un nombre.
- Reproducir el caso de prueba.

Para guardar un conjunto de pruebas, simplemente presiona el botón de guardar proyecto y descarga el archivo *.side* generado.

Puedes usar el panel a la derecha para observar y crear nuevos conjuntos de pruebas según tus necesidades.

Los proyectos se pueden exportar a diferentes lenguajes relacionados con Selenium, como Java, Python y C#.

Para aplicar correctamente, debemos seguir los siguientes pasos:
- Verificar que la acción del caso de prueba esté configurada.
- Agregar una nueva línea.
- Establecer el comando "assert text" (validación sobre una cadena de texto en el sitio web).
- Establecer el objetivo en el sitio web (puedes usar la opción de seleccionar).
- Establecer en valor el valor que estamos tratando de validar.
- (si se usa un comando como "assert element is present" no es necesario el valor).

**Consejo Profesional:** Una manera rápida de validar varios elementos es comenzar a grabar, hacer clic en los elementos para verificar y, después de detener el script, modificar el comando "click" por uno "assert".

[Aquí](https://www.selenium.dev/selenium-ide/docs/en/api/commands) puedes encontrar la documentación de Selenium IDE.

## Send KEYS

La función `send_keys` de Selenium es una herramienta fundamental para automatizar la interacción con elementos web que permiten la entrada de texto, como campos de texto, áreas de texto y cuadros de búsqueda. Esta función simula la escritura manual de un usuario en el elemento web objetivo, permitiendo ingresar datos, completar formularios y probar la funcionalidad de entrada de texto en aplicaciones web.

**Sintaxis básica:**

```python
element.send_keys(text_to_send)
```

**Parámetros:**

* `element`: Objeto WebElement que representa el elemento web al que se enviará el texto.
* `text_to_send`: Cadena de texto que se escribirá en el elemento web.

**Ejemplos de uso:**

**1. Completar un campo de nombre:**

```python
from selenium import webdriver

# Iniciar el navegador y abrir una página web
driver = webdriver.Chrome()
driver.get("https://www.ejemplo.com")

# Buscar el campo de nombre
nombre_campo = driver.find_element_by_id("nombre")

# Ingresar un nombre en el campo
nombre_campo.send_keys("Juan Pérez")
```

**2. Ingresar texto en un área de búsqueda:**

```python
from selenium import webdriver

# Iniciar el navegador y abrir una página web
driver = webdriver.Chrome()
driver.get("https://www.ejemplo.com/buscador")

# Buscar el área de búsqueda
area_busqueda = driver.find_element_by_name("busqueda")

# Ingresar un término de búsqueda en el área
area_busqueda.send_keys("camisas rojas")
```

**3. Escribir texto en un cuadro de comentarios:**

```python
from selenium import webdriver

# Iniciar el navegador y abrir una página web
driver = webdriver.Chrome()
driver.get("https://www.ejemplo.com/comentarios")

# Buscar el cuadro de comentarios
cuadro_comentarios = driver.find_element_by_css_selector("#comentarios textarea")

# Ingresar un comentario en el cuadro
cuadro_comentarios.send_keys("Excelente producto, lo recomiendo!")
```

**Funciones adicionales de `send_keys`:**

* **Enviar teclas especiales:** Puedes usar combinaciones de teclas especiales junto al texto, como `Ctrl+A` para seleccionar todo el texto o `Enter` para enviar el formulario.
* **Borrar texto existente:** Si el elemento ya contiene texto, puedes usar `send_keys("")` para borrarlo antes de ingresar el nuevo texto.
* **Simular escritura lenta:** Puedes ajustar la velocidad con la que se escribe el texto usando la opción `send_keys_with_delay(text, delay)` donde `delay` es el tiempo en milisegundos entre cada carácter.


## Navegación 

Selenium te ofrece diversas herramientas para navegar por el historial de una página web durante tus pruebas automatizadas. Entre las más comunes se encuentran los métodos `back()`, `forward()` y la función `execute_script()`. 

**1. Método `back()`:**

El método `back()` te permite retroceder un paso en el historial de la página web actual. Es como si presionaras el botón "Atrás" del navegador.

**Ejemplo de uso:**

Python

```Python
from selenium import webdriver

driver = webdriver.Chrome()
driver.get("https://www.ejemplo1.com")
driver.find_element_by_id("link2").click()  # Navegar a la página "ejemplo2.com"
driver.back()  # Regresar a "ejemplo1.com"
```

**2. Método `forward()`:**

El método `forward()` hace lo contrario que `back()`. Te permite avanzar un paso en el historial, como si presionaras el botón "Adelante" del navegador.

**Ejemplo de uso:**

Python

```python
from selenium import webdriver

driver = webdriver.Chrome()
driver.get("https://www.ejemplo1.com")
driver.find_element_by_id("link2").click()  # Navegar a "ejemplo2.com"
driver.back()  # Regresar a "ejemplo1.com"
driver.forward()  # Avanzar a "ejemplo2.com"
```

**3. Función `execute_script()`:**

La función `execute_script()` te brinda mayor flexibilidad para navegar por el historial. Puedes especificar la cantidad de pasos que deseas avanzar o retroceder usando el parámetro `n` dentro de la cadena `"window.history.go(n)"`.

**Ejemplo de uso:**

Python

```python
from selenium import webdriver

driver = webdriver.Chrome()
driver.get("https://www.ejemplo1.com")
driver.find_element_by_id("link2").click()  # Navegar a "ejemplo2.com"
driver.execute_script("window.history.go(-2)")  # Retroceder dos pasos (a "ejemplo1.com")
driver.execute_script("window.history.go(1)")  # Avanzar un paso (a "ejemplo2.com")
```

**Consideraciones importantes:**

- **Uso adecuado:** Utiliza cada método según tu necesidad. `back()` es ideal para retroceder un paso, mientras que `forward()` sirve para avanzar uno. Para mayor control, usa `execute_script()`.
- **Manejo de errores:** Asegúrate de que la página a la que deseas navegar exista y sea accesible. Si no existe, se generará una excepción.
- **Historial real:** Los métodos `back()` y `forward()` se basan en el historial real del navegador. Si navegas manualmente por la página, el historial cambia y estos métodos no funcionarán correctamente.
- **Alternativas:** Existen otras formas de navegar en Selenium, como usando enlaces o identificadores de elementos.

## Wait

## Errores Comunes

**1. NoSuchElementException:**

- **Razón:** No se encuentra el elemento especificado en el DOM.
- **Solución:** Verifique el selector CSS o XPath utilizado para identificar el elemento. Asegúrese de que sea preciso y coincida con el elemento en la página.

**2. StaleElementReferenceException:**

- **Razón:** El elemento al que se hace referencia ya no está presente en el DOM, posiblemente debido a cambios dinámicos en la página.
- **Solución:** Actualice la página antes de interactuar con el elemento o use el método `WebDriverWait` para esperar a que el elemento esté presente y estable.

**3. WebDriverException:**

- **Razón:** Un error general de WebDriver, que puede indicar varios problemas.
- **Solución:** Consulte el mensaje de error específico para obtener más información sobre la causa del problema. Los mensajes de error de WebDriver suelen ser descriptivos y pueden ayudar a identificar la raíz del problema.

**4. TimeoutException:**

- **Razón:** Una operación de Selenium no se completó dentro del tiempo de espera especificado.
- **Solución:** Aumente el tiempo de espera utilizando el método `implicitly_wait()` o `WebDriverWait`.

**5. ElementNotVisibleException:**

- **Razón:** El elemento especificado no es visible en la página.
- **Solución:** Verifique si el elemento está oculto por otros elementos o si requiere de acciones como desplazarse para ser visible.

**6. ElementNotInteractableException:**

- **Razón:** El elemento especificado no es interactuable, lo que significa que no se puede hacer clic en él, seleccionar texto o realizar otras acciones.
- **Solución:** Verifique si el elemento está deshabilitado o si requiere de acciones específicas para ser interactuable.

**7. InvalidSelectorException:**

- **Razón:** El selector CSS o XPath utilizado para identificar el elemento no es válido.
- **Solución:** Verifique la sintaxis del selector y asegúrese de que coincida con la estructura del DOM de la página.

**8. WebDriverTimeoutException:**

- **Razón:** Una operación de Selenium no se completó dentro del tiempo de espera especificado por `WebDriverWait`.
- **Solución:** Aumente el tiempo de espera utilizando el método `wait_timeout` de `WebDriverWait`.

**9. UnhandledDriverException:**

- **Razón:** Una excepción no manejada ocurrió dentro del controlador de WebDriver.
- **Solución:** Consulte el mensaje de error específico para obtener más información sobre la causa del problema. Puede ser necesario depurar el código para identificar la fuente de la excepción.

**10. NoAlertPresentException:**

- **Razón:** Se intentó interactuar con una alerta cuando no hay una presente en la página.
- **Solución:** Verifique si la alerta está realmente presente en la página antes de intentar interactuar con ella.

**11. NoSuchWindowException:**

- **Razón:** Se intentó acceder a una ventana que no existe.
- **Solución:** Verifique si la ventana a la que se hace referencia existe antes de intentar acceder a ella.

**12. WebDriverQUITRequestFailedException:**

- **Razón:** No se pudo cerrar el navegador o la sesión de WebDriver correctamente.
- **Solución:** Asegúrese de que no haya otras operaciones pendientes que puedan estar impidiendo que el navegador se cierre.

**13. InvalidElementStateException:**

- **Razón:** El estado del elemento no permite realizar la acción solicitada.
- **Solución:** Verifique el estado del elemento antes de intentar realizar la acción. Por ejemplo, un elemento puede estar deshabilitado o no ser interactuable.

**14. JavaScriptException:**

- **Razón:** Se produjo un error de JavaScript durante la ejecución de un comando de Selenium.
- **Solución:** Consulte la consola del navegador para obtener más información sobre el error de JavaScript. Puede ser necesario depurar el código JavaScript para identificar la causa del error.

**15. ScriptTimeoutException:**

- **Razón:** Un script de JavaScript ejecutado por Selenium no se completó dentro del tiempo de espera especificado.
- **Solución:** Aumente el tiempo de espera utilizando el método `execute_script_timeout` de `WebDriver`.

**16. NetworkConnectionException:**

- **Razón:** Se produjo un error de red al intentar comunicarse con el servidor web.
- **Solución:** Verifique su conexión a internet y asegúrese de que el servidor web esté disponible.

**17. FileNotDetectedException:**

- **Razón:** No se pudo encontrar el archivo especificado.
- **Solución:** Verifique la ruta del archivo y asegúrese de que existe y es accesible.
## Pruebas de Geolocalización con BiDirectional API/CDP

En Selenium 4, las pruebas de geolocalización con la BiDirectional API (BiDi API) o el Protocolo de Herramientas de Desarrollo de Chrome (CDP) permiten simular y probar la funcionalidad basada en geolocalización en aplicaciones web. Esta característica te permite establecer la ubicación geográfica del navegador a una latitud y longitud específicas.

Aquí tienes cómo puedes realizar pruebas de geolocalización con la BiDirectional API o CDP en Selenium 4 usando Java:

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;

public class GeolocationTestingExample {
    public static void main(String[] args) {
        // Configurar opciones de Chrome con opciones de CDP (Chrome DevTools Protocol)
        ChromeOptions options = new ChromeOptions();
        options.setExperimentalOption("w3c", false); // Requerido para la BiDirectional API

        // Habilitar simulación de geolocalización
        options.addArguments("--enable-features=GeolocationOverride");
        options.addArguments("--use-fake-ui-for-media-stream");
        options.addArguments("--use-fake-device-for-media-stream");
        options.addArguments("--geolocation=latitude,longitude");

        // Crear instancia de WebDriver
        WebDriver driver = new ChromeDriver(options);

        // Navegar a un sitio web que use geolocalización
        driver.get("https://www.example.com");

        // Realizar más acciones en el sitio web

        // Cerrar el navegador
        driver.quit();
    }
}
```

En este ejemplo:

1. Configuramos las opciones de Chrome usando `ChromeOptions` para configurar la instancia del WebDriver de Chrome.
2. Habilitamos el Protocolo de Herramientas de Desarrollo de Chrome (CDP) estableciendo la opción `w3c` en `false`. Esto es requerido para usar la BiDirectional API.
3. Habilitamos la simulación de geolocalización añadiendo argumentos específicos de línea de comando de Chrome:
   - `--enable-features=GeolocationOverride`: Habilita la función de anulación de geolocalización.
   - `--use-fake-ui-for-media-stream`: Utiliza una interfaz de usuario falsa para el flujo de medios (requerido para la geolocalización).
   - `--use-fake-device-for-media-stream`: Utiliza un dispositivo falso para el flujo de medios (requerido para la geolocalización).
   - `--geolocation=latitude,longitude`: Establece las coordenadas de latitud y longitud para la simulación de geolocalización.
4. Creamos una nueva instancia de `ChromeDriver` con las opciones configuradas.
5. Navegamos a un sitio web que use la funcionalidad de geolocalización.
6. Podemos realizar más acciones en el sitio web, como probar cómo responde a las coordenadas de geolocalización especificadas.
7. Finalmente, cerramos la instancia del WebDriver para cerrar el navegador.


## Pruebas Responsivas con BiDirectional API/CDP

Las pruebas responsivas con la BiDirectional API (BiDi API) o el Protocolo de Herramientas de Desarrollo de Chrome (CDP) permiten simular diferentes tamaños de pantalla y orientaciones de dispositivos para probar cómo tu aplicación web responde a los cambios en las dimensiones de la ventana y las orientaciones de los dispositivos.

Aquí tienes cómo realizar pruebas responsivas con la BiDirectional API o CDP en Selenium 4 usando Java:

```java
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import java.util.HashMap;
import java.util.Map;

public class ResponsiveTestingExample {
    public static void main(String[] args) {
        // Configurar opciones de Chrome con opciones de CDP (Chrome DevTools Protocol)
        ChromeOptions options = new ChromeOptions();
        Map<String, Object> deviceMetrics = new HashMap<>();
        deviceMetrics.put("width", 375); // Establecer ancho del dispositivo (por ejemplo, ancho del iPhone X)
        deviceMetrics.put("height", 812); // Establecer altura del dispositivo (por ejemplo, altura del iPhone X)
        deviceMetrics.put("pixelRatio", 3.0); // Establecer relación de píxeles del dispositivo (por ejemplo, relación de píxeles del iPhone X)
        Map<String, Object> mobileEmulation = new HashMap<>();
        mobileEmulation.put("deviceMetrics", deviceMetrics);
        mobileEmulation.put("userAgent", "Mozilla/5.0 (iPhone; CPU iPhone OS 11_0 like Mac OS X) AppleWebKit/604.1.38 (KHTML, like Gecko) Version/11.0 Mobile/15A372 Safari/604.1");
        options.setExperimentalOption("mobileEmulation", mobileEmulation);

        // Crear instancia de WebDriver
        WebDriver driver = new ChromeDriver(options);

        // Navegar a un sitio web y realizar pruebas
        driver.get("https://www.example.com");

        // Realizar más acciones en el sitio web

        // Cerrar el navegador
        driver.quit();
    }
}
```

En este ejemplo:

1. Configuramos las opciones de Chrome usando `ChromeOptions` para configurar la instancia del WebDriver de Chrome.
2. Definimos un mapa `deviceMetrics` para especificar las dimensiones y la relación de píxeles del dispositivo simulado. Aquí, establecemos el ancho, la altura y la relación de píxeles para simular un iPhone X.
3. Definimos otro mapa `mobileEmulation` para encapsular las métricas del dispositivo y la cadena del agente de usuario. La cadena del agente de usuario identifica el navegador y el sistema operativo que se está utilizando.
4. Establecemos la opción `mobileEmulation` en las opciones de Chrome para simular el dispositivo especificado.
5. Creamos una nueva instancia de `ChromeDriver` con las opciones configuradas.
6. Navegamos a un sitio web y realizamos pruebas sobre el comportamiento responsivo de la aplicación web.
7. Podemos realizar más acciones en el sitio web para validar su capacidad de respuesta bajo diferentes tamaños de pantalla y orientaciones de dispositivos.
8. Finalmente, cerramos la instancia del WebDriver para cerrar el navegador.


## Capture and Monitor Network Traffic

## Capture Performance Related Metrics 

## Network Emulation Testing

## Test Analysis and Reporting