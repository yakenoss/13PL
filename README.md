Manual de Usuario de 13PL (v1.0)
13PL es un lenguaje de programación interpretado, ligero y de sintaxis limpia, diseñado para la manipulación de estructuras de datos, funciones de primera clase y ejecución interactiva en consola.

1. Guía de Inicio Rápido
Compilar el Intérprete
Para generar el ejecutable principal del lenguaje desde el código fuente en Go:
go build -o 13pl .

Modos de Ejecución
Modo Interactivo (REPL): Inicia la consola ejecutando el binario sin argumentos:
./13pl
Ejecución de Archivos: Pasa la ruta de un script con extensión .13pl o .lang:
./13pl mi_programa.13pl

2. Variables y Tipos de Datos
Las variables en 13PL se declaran con la palabra clave var.
>> var x = 42
>> var mensaje = "Hola, 13PL"
>> var activo = true

Tipos Soportados
·	Enteros: 10, -5, 0
·	Textos (Strings): "Texto entre comillas"
·	Booleanos: true, false
·	Listas (Arrays): [1, 2, 3, 4]
·	Mapas (Diccionarios): {"clave": "valor", "edad": 25}
3. Estructuras de Control y Bucles
Condicionales
>> if (x > 10) { return true } else { return false }

Bucle while
Permite repetir bloques de código con soporte para interrupción anticipada (break) y salto de iteración (continue).
>> var i = 0
>> while (i < 5) { var i = i + 1 }

4. Funciones y Funciones Anónimas
Las funciones son ciudadanos de primera clase: se definen con fn y pueden asignarse a variables o pasarse como argumentos.
>> var sumar = fn(a, b) { return a + b }
>> sumar(5, 10)
=> 15

5. Biblioteca Estándar (Funciones Integradas)
13PL incluye funciones nativas para la inspección y transformación de listas:

Función --Descripción --Ejemplo de Uso
len(array | string) --Devuelve la longitud de un texto o lista.	--len([1, 2, 3]) —-> 3
push(array, elem) --Retorna una nueva lista con el elemento añadido al final.	--push([1, 2], 3) —-> [1, 2, 3]
pop(array) --Retorna el último elemento de una lista.	--pop([10, 20]) —-> 20
map(array, fn) --Aplica una función a cada elemento de la lista.	--map([1, 2], fn(x) { return x * 2 }) —-> [2, 4]
filter(array, fn) --Filtra la lista según una condición lógica.	--filter([1, 5, 10], fn(x) { return x > 2 }) —-> [5, 10]
reduce(array, fn, init) --Acumula los valores de la lista en un único resultado.	--reduce([1, 2, 3], fn(acc, x) { return acc + x }, 0) —-> 6

6. Ejemplo Completo de Código
Crea un archivo llamado script.13pl:
var numeros = [1, 2, 3, 4, 5, 6]

// Filtrar números pares (asumiendo función de condición)
var esMayorQueDos = fn(x) { return x > 2 }
var filtrados = filter(numeros, esMayorQueDos)

// Duplicar los valores filtrados
var duplicar = fn(n) { return n * 2 }
var resultado = map(filtrados, duplicar)

Ejecuta el script desde la terminal:
./13pl script.13pl

