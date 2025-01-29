# [AdventJS: Reto 23: 🔢 Encuentra los números perdidos](https://adventjs.dev/es/challenges/2024/23)
Los elfos están trabajando en un sistema para verificar las listas de regalos de los niños 👧👦. Sin embargo, ¡algunas listas están incompletas y faltan números!

Tu tarea es escribir una función que, dado un array de números, encuentre todos los números que faltan entre 1 y n (donde n es el tamaño del array o el número más alto del array).

Eso sí, ten en cuenta que:
- Los números pueden aparecer más de una vez y otros pueden faltar
- El array siempre contiene números enteros positivos
- Siempre se empieza a contar desde el 1
```javascript
findMissingNumbers([1, 2, 4, 6])
// [3, 5]

findMissingNumbers([4, 8, 7, 2])
// [1, 3, 5, 6]

findMissingNumbers([3, 2, 1, 1])
// []

findMissingNumbers([5, 5, 5, 3, 3, 2, 1])
// [4]
```
## Aproximación
### 1. Ordenar los números del array original
- Con el método `sort` se ordenarán ascendentemente los números: de esta manera podremos obtener el primer y el último número, que delimitará el rango del número para el siguiente paso.
### 2. Hacer un segundo array con los números consecutivos
- Teniendo el primero número, el número menor, y el último número, el mayor, tenemos delimitado un rango. Con este rango crearemos un nuevo array que tenga todos los números consecutivos dentro de nuestro rango. Utilizaremos el método `Array.from`.
### 3. Retornar los números que no se encuentren en el original
- Con el método `filter` e `include` vamos a retornar los números que no se encuentren en el array original. 
## Código
```typescript
function findMissingNumbers(nums: number[]): number[] {
  const sortedArr = nums.sort((a, b) => a - b);
  const seqArray = Array.from({ length: sortedArr[sortedArr.length-1]}, (_, index) => index+1);

  return seqArray.filter(x => !sortedArr.includes(x))
}
```
