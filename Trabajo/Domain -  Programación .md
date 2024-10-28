
**Domain description:**

```

```

**Knowledge Area:** [[Area - Labor]]


> [!NOTE] Index
> 1. [[#Algoritmos]]
> 2. [[#Estructuras de datos]]
> 3. [[#Complejidad algorítmica]]
> 4. [[#Loops]]
> 	1. [[#Test de los numeros primos]]
> 	2. [[#El tamiz de eratostenes]]
> 	3. [[#Fibonacci]]
> 	4. [[#Factorizacion de primos]]

## Algoritmos

Son secuencias finitas de instrucciones bien definidas, diseñadas para resolver un problema o realizar una tarea específica. Un algoritmo toma una entrada, la procesa de acuerdo a reglas específicas y produce una salida. La eficiencia de un algoritmo se mide en términos de tiempo de ejecución y uso de espacio de memoria. La elección de un algoritmo adecuado depende de la complejidad del problema y de los recursos disponibles.

Algunos ejemplos son:


## Estructuras de datos 

Son formas de organizar y almacenar datos en una computadora de manera que puedan ser accedidos y modificados eficientemente. Cada estructura de datos tiene sus propias operaciones permitidas y su propia complejidad algorítmica asociada a esas operaciones. La elección de una estructura de datos adecuada depende del tipo de datos que se van a almacenar y de las operaciones que se van a realizar sobre ellos.

Algunos ejemplos son:
- Arreglos
- Matrices 
- Linked lists
- Stack
- Queue
- Graphs
- Trees

## Complejidad algorítmica 

El análisis de algoritmos es una disciplina fundamental dentro de la ciencia de la computación que se encarga de estudiar la eficiencia de los algoritmos en términos de tiempo y espacio de ejecución. De manera más precisa, se busca cuantificar los recursos computacionales requeridos por un algoritmo en función del tamaño de la entrada. Para calcularlo se cuentan la cantidad de operaciones fundamentales en el algoritmo (suma, prodcto, asignación, return, comparaciones, operaciones bitwise)

**Importancia del Análisis**
 * Selección de Algoritmos: Permite evaluar y comparar la eficiencia de distintos algoritmos para un mismo problema, facilitando la elección del más adecuado según los requerimientos de la aplicación.
 * Optimización de Código: Identifica las secciones de un algoritmo que dominan el tiempo de ejecución, permitiendo enfocar los esfuerzos de optimización en las partes más críticas.
 * Escalabilidad: Proporciona una estimación del comportamiento de un algoritmo ante el crecimiento de los datos de entrada, lo cual es esencial para el diseño de sistemas que puedan manejar grandes volúmenes de información.

**Medición de la Complejidad**
La complejidad de un algoritmo se expresa típicamente mediante notación asintótica, que describe el comportamiento del algoritmo cuando el tamaño de la entrada tiende a infinito. Las notaciones más utilizadas son:
 * Notación O grande (O): Cota superior asintótica. Representa un límite superior del tiempo de ejecución, es decir, el algoritmo no tardará más que una cierta función del tamaño de la entrada.
 * Notación Omega (Ω): Cota inferior asintótica. Indica un límite inferior del tiempo de ejecución, asegurando que el algoritmo tardará al menos una cierta cantidad de tiempo.
 * Notación Theta (Θ): Cota ajustada asintótica. Describe tanto una cota superior como inferior, indicando que el tiempo de ejecución del algoritmo es proporcional a una determinada función del tamaño de la entrada.

**Clases de Complejidad Comunes**
 * O(1): Complejidad constante. El tiempo de ejecución es independiente del tamaño de la entrada.
 * O(log n): Complejidad logarítmica. El tiempo de ejecución crece muy lentamente con el tamaño de la entrada.
 * O(n): Complejidad lineal. El tiempo de ejecución crece proporcionalmente al tamaño de la entrada.
 * O(n²): Complejidad cuadrática. El tiempo de ejecución crece cuadráticamente con el tamaño de la entrada.
 * O(2^n): Complejidad exponencial. El tiempo de ejecución crece de manera explosiva con el tamaño de la entrada.


## Loops

#### Test de los numeros primos

Brute force approach - *O(n)*

```
For - loop:

for i -> 2, n-1:
	if (n % i == 0):
		return false;
	return true
```

Despues de analizar, podemos notar que existe un algoritmo con menor complejidad O(sqrt(n)):

```
Por definicion un numero NO es primo si es el producto de 2 numeros entre el rango de [2, n-1], por lo tanto podemos decir que si un numero no es primo si se cumple que n = a*b, entonces podemos despegar y notar que b= n/a, por esta propiedad, sabemos que a <= b, esto implica que a*b >= a^2, y por lo tanto, a <= squrt(n)

El algoritmo queda como:

for i -> 2, 2Sqrt(n):
	if (n % i == 0):
		return false;
	return true
	
```


#### El tamiz de eratostenes

El tamiz de eratostenes es un algoritmo antiguo para encontrar todos los numeros primos dado un numero n. Una manera basica de verlo es que cuando encuentra un numero primo, este genera todos sus mutiplos y los marca como no primos.

*O(limite * log(limit))*
```
for i -> 2, limit/2:
	if i es primo:
		for j -> i*2, limite, j+=i:
		j no es primo
```

#### Fibonacci

Metodo iterativo:

```
def fibonacci_iterativo(n):
    if n <= 1:
        return n
    else:
        a, b = 0, 1
        for _ in range(2, n+1):
            a, b = b, a+b
        return b

```

Metodo recursivo:

```
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n-1) + fibonacci(n-2)

```

#### Factorizacion de primos

La factorizacion de primos consiste en encontrar que numeros primos se multiplican juntos para obtener el numero original.

```
def factorPrimo(n)
	d = 2
	while(1LL * d * d <= n && n > 1):
		k = 0
		while(n % d == 0):
			k++
			n /= d
		if(k > 0):
			len++
			f[len] = d
			expo[len] = k
		d++
	if(n > 1):
	    len++
	    f[len] = n
		expo[len] = 1
	
```
