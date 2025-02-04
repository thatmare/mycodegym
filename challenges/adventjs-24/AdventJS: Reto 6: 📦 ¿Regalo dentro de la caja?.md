# [AdventJS: Reto 6: 📦 ¿Regalo dentro de la caja?](https://adventjs.dev/es/challenges/2024/6)
Ya hemos empaquetado cientos de regalos 🎁… pero a un elfo se le ha olvidado revisar si el regalo, representado por un asterisco *, está dentro de la caja.

La caja tiene un regalo (*) y cuenta como dentro de la caja si:
- Está rodeada por # en los bordes de la caja.
- El * no está en los bordes de la caja.

Ten en cuenta entonces que el * puede estar dentro, fuera o incluso no estar. Y debemos devolver true si el * está dentro de la caja y false en caso contrario.
```javascript
inBox([
  "###",
  "#*#",
  "###"
]) // ➞ true

inBox([
  "####",
  "#* #",
  "#  #",
  "####"
]) // ➞ true

inBox([
  "#####",
  "#   #",
  "#  #*",
  "#####"
]) // ➞ false

inBox([
  "#####",
  "#   #",
  "#   #",
  "#   #",
  "#####"
]) // ➞ false
```

## Aproximación
### 1. Iterar sobre el array a partir del índice 1 y hasta el índice -1.
- Ya que estamos buscando el regalo en toda la caja **menos** en el borde, iniciaremos a iterar en el index 1 (excluyendo el 0), y hasta el -1 (excluyendo el último). Lo haremos con un bucle `for`.
### 2. Iterar sobre la cadena de texto a partir del índice 1 y hasta el índice -1.
- Ya que estamos buscando el regalo en toda la caja **menos** en el borde, iniciaremos la iteración en el index 1 de la cadena, y hasta el -1, con un bucle `for`.
### 3. Buscar el *
- Habiendo excluido el margen de la caja, si se encuentra algún "*" dentro de los índices que limitamos, arrojar `true`. Cualquier otro caso, arrojar `false`.

## Código
```javascript
/** @param {string[]} box
 *  @returns {boolean} True if the gift is inside the box
 */
function inBox(box) {
  for (let i = 1; i < box.length - 1; i++) {
    for (let j = 1; j < box[i].length - 1; j++) {
      if (box[i][j] === '*') {
        return true;
      }
    }
  }
  
  return false;
}
```
