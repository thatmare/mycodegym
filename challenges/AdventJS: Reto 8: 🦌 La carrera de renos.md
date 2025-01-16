# AdventJS: Reto 8: 🦌 La carrera de renos
[AdventJS: Reto 8: 🦌 La carrera de renos](https://adventjs.dev/challenges/2024/8)

It's time to select the fastest reindeer for Santa's journeys! 🦌🎄 Santa Claus has organized exciting reindeer races to determine which ones are in the best shape.

Your task is to display each reindeer's progress on a snow track in isometric format.

The information you receive:
```
indices: An array of integers representing each reindeer's progress on the track:
0: The lane is empty.
Positive number: The reindeer's current position from the beginning of the track.
Negative number: The reindeer's current position from the end of the track.
length: The length of each lane.
```
Return a string representing the race track:

Each lane has exactly length positions filled with snow (~).
Each reindeer is represented with the letter r.
Lanes are numbered at the end with /1, /2, etc.
The view is isometric, so the lower lanes are shifted to the right.
## Releer el problema
Es momento de elegir al reno más rápido. Santa Claus ha organizado una carrera de renos para determinar quién tiene la mejor condiciona.

Tu tarea es mostrar el progreso de cada reno en su trineo en un formato isométrico. La información que recibes:
```
indices: un array de números que representa el progreso de cada reno en su carril:
  0: el carril está solo
  Número positivo: la posición del reno al principio de la carrera
  Número negativo: La posición del reno al final de la carrera
length: la longitud de cada carril
```

## Ejemplos
```
drawRace([0, 5, -3], 10)
/*
  ~~~~~~~~~~ /1 <- indices[0] no tiene r porque su valor es 0,  longitud de nieve ~ es de 10
 ~~~~~r~~~~ /2 <- indices[1] tiene r en str[5]
~~~~~~~r~~ /3 <- indices[2] tiene r en str[-3]
*/

drawRace([2, -1, 0, 5], 8)
/*
   ~~r~~~~~ /1
  ~~~~~~~r /2
 ~~~~~~~~ /3
~~~~~r~~ /4
*/

drawRace([3, 7, -2], 12)
/*
  ~~~r~~~~~~~~ /1
 ~~~~~~~r~~~~ /2
~~~~~~~~~~r~ /3
*/
```
## Aproximación
### 1. Crear `indices.length` cantidad de carrles con `length` de nieve
  - Con el método Array.from() vamos a crear un array que contenga los carriles.
  - Para cada carril, llenaremos de nieve con la longitud dada. Será una cadena de texto. 
  - Es necesario que este sea el primer paso sin considerar espacios o números de carril, pues aquí la longitud de la cadena de texto es importante para colocar la "r"
### 2. Convertir las cadenas de texto en array para agregar la "r"
  - Vamos a convertir la cadena de texto en array para usar el método `.splice()` y así reemplazar la nieve con "r" en la posición dada.
### 3. Agregar espacios y números de carril
  - Los espacios al inicio para desplazar el carril tiene la fórmula `indices.length - (array[0] + 1)`
  - El número de carril es dado por la fórmula `index + 1`
  - Agregar el salto de línea `\n`
  - Converir a string con `.join('')`

## Código
```javascript
function drawRace(indices, length) {
  // Hacer array con longitud indices.length: es decir, si la longitud de indices es 3, insertar 3 elementos
  // Cada elemento será una cadena de texto, en este caso, de nieve (~) y repetirla length veces
  const arr1 = Array.from( { length: indices.length }, () => '~'.repeat(length))

  // Para cada elemento/carril, convertirlo en array
  const arr2 = arr1.map((x) => [...x])

  // Iterar sobre los índices
  for (let i = 0; i < indices.length; i++) {
    if(indices[i] !== 0 ) { // Si el índice es distinto a 0, reemplazar con "r" en la posición de indices[i]
      arr2[i].splice(indices[i], 1, 'r')
    }
  }

  return arr2.map((x, i)=> ' '.repeat(indices.length - (i + 1)) + x.join('') + ` /${i + 1}`).join('\n') // unir los arrays con el espacio, no. de carril y salto de línea
}
```
Esta solución obtuvo 2/5 estrellas. ⭐⭐
## Optimización
La solución de ⭐⭐⭐⭐⭐ estrellas está dada por [marcocode24](https://github.com/marcode24/adventjs-solutions/blob/main/2024/08-la-carrera-de-renos/README.md)
## Enlaces y temas de interés
- [`Array.from()` en MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from), [Crear un array a partir de la longitud en StackOverflow](https://stackoverflow.com/questions/40528557/how-does-array-fromlength-5-v-i-i-work).
- [`splice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice): Método para reemplazar elemento en array en n posición y m cantidad de veces. [JavaScript Splice: Como utilizar el metodo .splice() de arreglo en JS](https://www.freecodecamp.org/espanol/news/javascript-splice-como-ulitizar-el-metodo-splice-de-arreglo-en-js/)
