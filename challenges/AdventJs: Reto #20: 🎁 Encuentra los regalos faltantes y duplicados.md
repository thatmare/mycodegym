# [AdventJs: Reto #20: 🎁 Encuentra los regalos faltantes y duplicados](https://adventjs.dev/es/challenges/2024/20)
Santa Claus 🎅 está revisando la lista de regalos que debe entregar esta Navidad. Sin embargo, algunos regalos faltan, otros están duplicados, y algunos tienen cantidades incorrectas. Necesita tu ayuda para resolver el problema.

Recibirás dos arrays:

- `received`: Lista con los regalos que Santa tiene actualmente.
- `expected`: Lista con los regalos que Santa debería tener.

Tu tarea es escribir una función que, dado received y expected, devuelva un objeto con dos propiedades:

- `missing`: Un objeto donde las claves son los nombres de los regalos faltantes y los valores son las cantidades que faltan.
- `extra`: Un objeto donde las claves son los nombres de los regalos extra o duplicados y los valores son las cantidades que sobran.

Ten en cuenta que:

- Los regalos pueden repetirse en ambas listas.
- Las listas de regalos están desordenadas.

Si no hay regalos que falten o sobren, las propiedades correspondientes (missing o extra) deben ser objetos vacíos.
```javascript
fixGiftList(['puzzle', 'car', 'doll', 'car'], ['car', 'puzzle', 'doll', 'ball'])
// Devuelve:
// {
//   missing: { ball: 1 },
//   extra: { car: 1 }
// }

fixGiftList(
  ['book', 'train', 'kite', 'train'],
  ['train', 'book', 'kite', 'ball', 'kite']
)
// Devuelve:
// {
//   missing: { ball: 1, kite: 1 },
//   extra: { train: 1 }
// }

fixGiftList(
  ['bear', 'bear', 'car'],
  ['bear', 'car', 'puzzle', 'bear', 'car', 'car']
)
// Devuelve:
// {
//   missing: { puzzle: 1, car: 2 },
//   extra: {}
// }

fixGiftList(['bear', 'bear', 'car'], ['car', 'bear', 'bear'])
// Devuelve:
// {
//   missing: {},
//   extra: {}
// }
```
## Aproximación
### 1. Crear objetos de clave el juguete, de valor la cantidad de juguetes
- Con el método `reduce()` iteramos sobre el array y acumulamos dentro de un objeto.
  - Si no se encuentra el juguete, lo agregamos con valor 1.
  - Si ya se encuentra, le agregamos 1.
### 2. Objeto resultante
- Hacemos un objeto con dos llaves: `missing` y `extra`. Ambas llaves con objetos vacíos.
### 3. Recorrer el objeto de jugetes esperados y comparar contra el objeto de juguetes recuperados
- Utilizamos el bucle `for...in` con las llaves del objeto.
  - Si en el objeto de juguetes recibidos NO se encuentra la llave de los objetos esperados, agregamos en `result.missing` el juguete y su cantidad.
  - Si un juguete esperado se encuentra en los juguetes recibidos pero es mayor en cantidad que este último, agregamos en `result.missing` la cantidad de esperados menos la de recibidos.
  - Si un juguete esperado se encuentra en los juguetes recibidos pero es menor, agregamos en `result.extra` la cantidad de recibidos menos la de esperados.

## Código
```typescript

function fixGiftList(received: string[], expected: string[]): { missing: Record<string, number>, extra: Record<string, number> } {
  const receivedObj = received.reduce((acc, item) => {
    if(!acc[item]) {
      acc[item] = 1
    } else if (acc[item]) {
      acc[item] += 1
    }
    return acc
  }, {})
  
  const expectedObj = expected.reduce((acc, item) => {
    if(!acc[item]) {
      acc[item] = 1
    } else if (acc[item]) {
      acc[item] += 1
    }
    return acc
  }, {})
 	
  const result = { missing: {}, extra: {} }
  
  for (const key in expectedObj) {
    if (!receivedObj[key]) {
      Object.assign(result.missing, { [key] : expectedObj[key]} )
    } else if (expectedObj[key] > receivedObj[key]) {
      Object.assign(result.missing, { [key]: expectedObj[key] - receivedObj[key]})
    } else if (expectedObj[key] < receivedObj[key]) {
      Object.assign(result.extra, { [key]: receivedObj[key] - expectedObj[key]})
    }
  }

  return result
}

```
## Optimización
## Enlaces y temas de interés
