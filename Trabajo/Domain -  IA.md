
**Domain description:**

```

```

**Knowledge Area:** [[Domain - Testing & QA]]


> [!NOTE] Index
> 1. [[#Large Language Models]]
> 	1. [[#Prompt Engineering]]
> 	3. [[#LLM Testing]]
> 2. Machine Learning
> 3. 

## Large Language Models

Un LLM son basicamente dos archivos, uno de parametros y otro de running (normalmente escrito de python o en C), el archivo de parametros es un archivo gigante de texto, basicamente el corpus utilizado para entrenar a un IA, el archivo de parametros es normalmente un archivo comprimido de 140GB que comprime aproximadamente 10TB de texto.

Un LLM funciona basicamente prediciendo la siguiente palabra mas probable, para su creacion la primera fase llamada pre entrenamiento, simplemente aprende a como es que el texto se estructura, se alucinan elementos a partir del archivo de parametros.

Seguido de ello viene la etapa que conocemos como fine tuning, con el esencialmente le damos al LLM muchos ejemplos de como a los humanos les gustarian sus respuestas. Entonces a traves de repetir este proceso llamado "feeding", el LLM aprende.

La ultima parte de la creacion llamada "reinforcement learning", consiste en que despues del "pre-training" y el "fine tuning", le haremos una pregunta al LLM y contestaremos si la respuesta es correcta o no.

La manera en la que el LLM entiende si una respuesta es correcta y "aprende", es asignando pesos a los tokens que se generan de un prompt, en linguistica computacional existe un termino llamado tokenizacion y normalizacion, estos dos son el proceso que se lleva a cabo para separar las palabras en un contexto que la red neuronal entienda, y  a través del proceso de "reinforcement training", es que le asignamos a los diferentes tokens un peso para que el LLM pueda hacer una mejor prediccion en la siguientes iteraciones.

Todos los LLM tienen un limite de tokens que pueden correr, dicho de manera simple, existe un limite en la informacion que pueden retener, algunos LLM tienen un limite de tokens de 2M y otros unicamente de 4K.

El ranking de los mejores LLM lo puedes encontrar [aqui](https://chat.lmsys.org). 
El ranking de los mejores LLM Open Source lo puedes encontrar [aqui](https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard).

Los LLM suelen ser ejecutados en componentes de necesidades computacionales que pueden ser desafiantes, como intel i7 + GPU + 10GB VRAM etc. Tal requerimiento aplica primordialmente para los modelos mas grandes y de mas alta precisión,  uno de los metodos para poder lograr que modelos grandes se ejecuten en computadoras pequeñas, se le llama **Quantization**, cuya idea básica se reduce a en vez de procesar y guardar los numeros en un modelo con alta precision (32 bit), podemos reducirlo a con menos precisión (8 bit o 4 bit), esto logra ahorrar memoria, calculos mas rápidos.

Una quantizacion a 8 bits o Q8, es una reduccion moderada que ofrece un buen compromiso entre espacio de moria, performance computacional y precision del modelo, por otro lado, Q4, ahorra mucha mas memoria, no obstante es importante recordar que un exceso de ahorro puede llevar a una gran perdida de la precision.
#### Prompt Engineering

#### LLM Testing
