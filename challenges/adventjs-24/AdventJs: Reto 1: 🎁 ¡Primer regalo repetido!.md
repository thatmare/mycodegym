# [AdventJs: Reto 1: 🎁 ¡Primer regalo repetido!](https://adventjs.dev/es/challenges/2024/1)
Santa Claus 🎅 ha recibido una lista de números mágicos que representan regalos 🎁, pero algunos de ellos están duplicados y deben ser eliminados para evitar confusiones. Además, los regalos deben ser ordenados en orden ascendente antes de entregárselos a los elfos.

Tu tarea es escribir una función que reciba una lista de números enteros (que pueden incluir duplicados) y devuelva una nueva lista sin duplicados, ordenada en orden ascendente.
```javascript
const gifts1 = [3, 1, 2, 3, 4, 2, 5]
const preparedGifts1 = prepareGifts(gifts1)
console.log(preparedGifts1) // [1, 2, 3, 4, 5]

const gifts2 = [6, 5, 5, 5, 5]
const preparedGifts2 = prepareGifts(gifts2)
console.log(preparedGifts2) // [5, 6]

const gifts3 = []
const preparedGifts3 = prepareGifts(gifts3)
console.log(preparedGifts3) // []
// No hay regalos, la lista queda vacía
```
## Aproximación
### 1. Ordenar de manera ascendente los números
- Utilizar el método `sort()` para ordenar los números ascendentemente.
### 2. Eliminar aquellos repetidos
- Utilizar un bucle para eliminar aquellos que sean iguales (se repitan).
## Código
```typescript
function prepareGifts(gifts: number[]): number[] {
  const giftsSort = gifts.sort((a, b) => a - b);
  const noRepeatedGifts = [];

  for (let i = 0; i < giftsSort.length; i++) {
    if (giftsSort[i] !== giftsSort[i+1]) {
      noRepeatedGifts.push(giftsSort[i]);
    }
  }

  return noRepeatedGifts
}
```
## Enlaces y temas de interés
- [`sort()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
- [Bucle `for`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/for)
