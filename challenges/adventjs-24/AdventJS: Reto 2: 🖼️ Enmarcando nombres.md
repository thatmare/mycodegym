# [AdventJS: Reto 2: 🖼️ Enmarcando nombres](https://adventjs.dev/es/challenges/2024/2)
Santa Claus 🎅 quiere enmarcar los nombres de los niños buenos para decorar su taller 🖼️, pero el marco debe cumplir unas reglas específicas. Tu tarea es ayudar a los elfos a generar este marco mágico.

Reglas:
- Dado un array de nombres, debes crear un marco rectangular que los contenga a todos.
- Cada nombre debe estar en una línea, alineado a la izquierda.
- El marco está construido con * y tiene un borde de una línea de ancho.
- La anchura del marco se adapta automáticamente al nombre más largo más un margen de 1 espacio a cada lado.

Ejemplo de funcionamiento:
```javascript
createFrame(['midu', 'madeval', 'educalvolpz'])

// Resultado esperado:
***************
* midu        *
* madeval     *
* educalvolpz *
***************

createFrame(['midu'])

// Resultado esperado:
********
* midu *
********

createFrame(['a', 'bb', 'ccc'])

// Resultado esperado:
*******
* a   *
* bb  *
* ccc *
*******

createFrame(['a', 'bb', 'ccc', 'dddd'])
```
## Aproximación
### 1. Observar el resultado de la cadena de texto
```javascript
createFrame(['midu', 'madeval', 'educalvolpz'])
// Cadena de mayor longitud: educalvolpz, longitud: 11

// Resultado esperado:
*************** // longitud: 15 = cadenaMayorLongitud + 4
* midu        * // '*' = 1, ' ' = 1, 'midu' = 4, ' ' = 8, '*' = 1
* madeval     * // 1, 1, 7, 5, 1
* educalvolpz * // 1, 1, 11, 1, 1
*************** // 15
```
- La longitud del cuadro está dado por la cadena de mayor longitud más 4.
- Dentro de una línea, siempre hay '* ' al inicio y un '*' al final.
- El espacio sobrante después del nombre está dado por la longitud del cuadro menos la longitud del nombre actual menos los 4 espacios. 
### 2. Obtener la cadena de texto con mayor longitud
- Utilizamos el método `Math.max` para obtener el mayor número de un array.
- Este array será un mapeo del array de nombres.
- Sumamos 4.
### 3. Crear los nombres en el marco considerando el espacio sobrante
- Crear un array a partir de la longitud de `names`.
- Cada elemento del array por default lleva '* ', concatenamos el nombre actual `name[index]`, concatenamos el espacio restando la longitud del cuadro, menos la longitud del nombre, menos 4, y finalmente concatenamos ' *'.
### 4. Crear líneas horizontales del marco
- Utilizamos `.repeat` para insertar '*' con la longitud del cuadro.
### 5. Concatenamos con salto de línea
- Retornamos las líneas horizontales y el array con el salto de línea '\n'.
## Código
```typescript
function createFrame(names: string[]): string {
  const frameWidth = Math.max(...names.map((i) => i.length)) + 4;
  const namesInFrame = Array.from({ length: names.length}, (_, index) => 
  	('* ' + names[index] + ' '.repeat((frameWidth - names[index].length) - 4) +' *')
  );
  const frameLines = '*'.repeat(frameWidth);

  return frameLines + '\n' + namesInFrame.join('\n') + '\n' + frameLines
}
```
## Enlaces y temas de interés
- [`Math.max()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
- [`repeat()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String/repeat)
- [`join()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
- [`Array.from`](https://runebook.dev/es/docs/javascript/global_objects/array/from)
