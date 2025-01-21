# AdventJS: Reto 14: 🦌 Acomodando los renos
[AdventJS: Reto 14: 🦌 Acomodando los renos](https://adventjs.dev/es/challenges/2024/14)

Los renos necesitan moverse para ocupar los establos, pero no puede haber más de un reno por establo. Además, para que los renos estén cómodos, debemos minimizar la distancia total que recorren para acomodarse.

Tenemos dos parámetros:
- reindeer: Un array de enteros que representan las posiciones de los renos.
- stables: Un array de enteros que representan las posiciones de los establos.

Hay que mover cada reno, desde su posición actual, hasta un establo. Pero hay que tener en cuenta que sólo puede haber un reno por establo. Tu tarea es calcular el mínimo número de movimientos necesarios para que todos los renos acaben en un establo.

Nota: Ten en cuenta que el array de establos siempre tendrá el mismo tamaño que el array de renos y que siempre los establos serán únicos.

## Releer
- Debemos retornar la suma de movimientos de los renos hacia los establos.
- Antes de sumar los movimientos, hay que compararlos para identificar cuál posición es la más cercana, por lo cual se harían la menor cantidad de movimientos para acomodarlos.
- Dos inputs: dos arrays de números, uno indicando la posición actual de los renos y el segundo indicando los establos disponibles.
```javascript
function minMovesToStables(reindeer: number[], stables: number[]): number {
  // Código aquí
  return 0
}
```

## Ejemplos
```javascript
minMovesToStables([2, 6, 9], [3, 8, 5]) // -> 3
// Explicación:
// Renos en posiciones: 2, 6, 9
// Establos en posiciones: 3, 8, 5
// 1er reno: se mueve de la posición 2 al establo en la posición 3 (1 movimiento).
// 2do reno: se mueve de la posición 6 al establo en la posición 5 (1 movimiento)
// 3er reno: se mueve de la posición 9 al establo en la posición 8 (1 movimiento).
// Total de movimientos: 1 + 1 + 1 = 3 movimientos

minMovesToStables([1, 1, 3], [1, 8, 4]) // -> 8
// Explicación:
// Renos en posiciones: 1, 1, 3
// Establos en posiciones: 1, 8, 4
// 1er reno: no se mueve (0 movimientos)
// 2do reno: se mueve de la posición 1 al establo en la posición 4 (3 movimientos)
// 3er reno: se mueve de la posición 3 al establo en la posición 8 (5 movimientos)
// Total de movimientos: 0 + 3 + 5 = 8 movimientos
```
## Aproximación
### 1. Ordenar los números de menor a mayor
- Ya que los arrays tienen la misma longitud, y queremos asignar las posiciones a la más cercana posible, vamos a ordenar de menor a mayor con el método `sort()`.
### 2. Recorrer los arrays y comparar los elementos
- Por medio de un bucle, comparar los elementos en las mismas posiciones: si `arr1[i]` es mayor que `arr2[i]`, restar `arr1[i]` a `arr2[i]` y viceversa.
### 3. Insertar resultados de resta en un array y sumarlos
- Los resultados de la operación anterior, almacenarlos en un nuevo arrary.
- En este array, sumar los números con `reduce()`.
## Código
```javascript
function minMovesToStables(reindeer, stables) {
  const orderedReindeer = reindeer.sort();
  const orderedStables = stables.sort();
  let arr1 = [];
  for (let i = 0; i < orderedReindeer.length; i++) {
    if (orderedReindeer[i] > orderedStables[i]) {
      arr1.push(orderedReindeer[i] - orderedStables[i]) 
    } else {
      arr1.push(orderedStables[i] - orderedReindeer[i])
    }
}  
 return arr1.reduce((acc, item) => acc + item, 0)
}
```
Obtuvo ⭐⭐⭐⭐⭐

## Enlaces y temas de interés
- [`sort()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/sort): Ordena los elementos de un array y los devuelve ordenados.
- [`reduce()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce): Ejecuta una función reductora en un array.
- [`for`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/for): Bucle para recorrer, en este caso, los arrays. 
