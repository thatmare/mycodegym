# [AdventJS: Reto #16: ❄️ Limpiando la nieve del camino](https://adventjs.dev/es/challenges/2024/16)
Los elfos están trabajando arduamente para limpiar los caminos llenos de nieve mágica ❄️. Esta nieve tiene una propiedad especial: si dos montículos de nieve idénticos y adyacentes se encuentran, desaparecen automáticamente.

Tu tarea es escribir una función que ayude a los elfos a simular este proceso. El camino se representa por una cadena de texto y cada montículo de nieve un carácter.

Tienes que eliminar todos los montículos de nieve adyacentes que sean iguales hasta que no queden más movimientos posibles.

El resultado debe ser el camino final después de haber eliminado todos los montículos duplicados:
```javascript
removeSnow('zxxzoz') // -> "oz"
// 1. Eliminamos "xx", quedando "zzoz"
// 2. Eliminamos "zz", quedando "oz"

removeSnow('abcdd') // -> "abc"
// 1. Eliminamos "dd", quedando "abc"

removeSnow('zzz') // -> "z"
// 1. Eliminamos "zz", quedando "z"

removeSnow('a') // -> "a"
// No hay montículos repetidos
```
## Aproximación
### 1. Recorrer la cadena de texto y encontrar coincidencias
- Vamos a convertir el string en un array con el spread operator `[...]`. Esto es para poder utilizar el método `splice()` más adelante. 
- Vamos a comparar el caracter en arr[i] contra arr[i+1].
### 2. Remover ambos caracteres repetidos
- Con el método `splice()` vamos a quitar ambos caracteres.
### 3. Retornar un string
- Utilizamos `join()` para retornar una cadena de texto.
### 4. Implementamos la recursividad
- Dado que, tenemos que primero quitar los caracteres consecutivos, y luego con esa cadena volver a quitar los consecutivos, vamos a implementar la recursividad.
- Creamos una variabke `change` que sirva como "bandera" para establecer nuestro caso borde.
- Si `change` es `false`, retornamos el string; si `change` es `true`, retornamos la función con el array convertido a string. 
## Código
```typescript
function removeSnow(s: string): string {
  let arr = [...s]
  let change = false;

  for (let i = 0; i < arr.length-1; i++) {
    if (arr[i] === arr[i+1]) {
      arr.splice(i, 2)
      change = true;
    }
  }

  if (!change) {
    return arr.join('')
  } else if (change) {
    return removeSnow(arr.join(''))
  }
}
```
## Optimización
- La solución anterior obtuvo ⭐⭐.
- [Una solución con ⭐⭐⭐⭐⭐ es la de dalo-dev](https://github.com/dalo-dev/adventJS-2024/blob/main/solutions/day-16/day-16.md): él utliza la estructura de pilas (_stack_ en inglés).

## Enlaces y temas de interés
- [Cómo entender la recursión en Javascript](https://www.freecodecamp.org/espanol/news/como-entender-recursividad-en-javascript/)
- [Método splice()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
- [Método join()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
- [Estructura de datos de pila (_stack_)](https://www.geeksforgeeks.org/introduction-to-stack-data-structure-and-algorithm-tutorials/)
