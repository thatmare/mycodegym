# AdventJS: Reto 12: 💵 ¿Cuánto cuesta el arbolito?
[AdventJS: Reto 12: 💵 ¿Cuánto cuesta el arbolito?](https://adventjs.dev/challenges/2024/12)

*You are in a very special market where Christmas trees 🎄 are sold. Each one comes decorated with a series of very peculiar ornaments, and the price of the tree is determined by the ornaments it has.*
```
*: Snowflake - Value: 1
o: Christmas Ball - Value: 5
^: Decorative Tree - Value: 10
#: Shiny Garland - Value: 50
@: Polar Star - Value: 100
```
*Normally, you would sum up all the values of the ornaments and that's it… But, watch out! If an ornament is immediately to the left of another of greater value, instead of adding, its value is subtracted.*

## Releer el problema
Estás en una tienda de Navidad donde se venden pinitos navideños. Cada uno viene decorado con diferentes ornamentos, y el precio del arbol también contempla los ornamentos que tiene. 
```
*: Copito de nieve - Valor: 1 
o: Esfera - Valor: 5
^: Ornamento de arbolito - Valor: 10
#: Guirnalda brillante - Valor: 50
@: Estrella polar - Valor: 100
```
Normalmente, sumarías los valores de los ornamentos... pero, ¡cuidado! Si un ornamento está al lado de uno de mayor valor, en vez de sumar, vas a restar.

```typescript
// Parámetros: string
// Valor de retorno: number
function calculatePrice(ornaments: string): number {
  // Código aquí...
  return 0
}
```
## Ejemplos
```
calculatePrice('***')  // 3   (1 + 1 + 1)
calculatePrice('*o')   // 4   (-1 + 5)
calculatePrice('o*')   // 6   (5 + 1)
calculatePrice('*o*')  // 5  (-1 + 5 + 1) 
calculatePrice('**o*') // 6  (1 - 1 + 5 + 1) 
calculatePrice('o***') // 8   (5 + 1 + 1 + 1)
calculatePrice('*o@')  // 94  (-1 + 5 + 100)
calculatePrice('*#')   // 49  (-1 + 50)
calculatePrice('@@@')  // 300 (100 + 100 + 100)
calculatePrice('#@')   // 50  (-50 + 100)
calculatePrice('#@Z')  // undefined (Z no tiene valor)
```

## Aproximación
1. Almacenar los valores en un objeto.
  - Lo primero que haremos será almacenar los ornamentos con sus precios, de tal manera que podamos identificar el valor por ornamento: `'*' : 1`.
2. Iterar sobre la cadena de texto y comparar
  - Con un loop `for` vamos a recorrer la cadena de texto (los ornamentos). Compararemos el elemento actual con el siguiente.
  - La condición dada es que, si el número de la izquierda es menor al de la derecha, el número de la izquierda se resta: es decir, se pasa como negativo.
3. Almacenar los valores en un array
  - Para realizar la suma, almacenamos los precios y sumamos con `reduce`.
## Código
```javascript
function calculatePrice(ornaments) {
 const example = {
 	'*': 1, 
  'o': 5,
  '^': 10,
  '#': 50,
  '@': 100
 }
 const sum = [] // Array vacío donde almacenaremos los valores de los ornamentos.
	for (let i = 0; i < ornaments.length; i++) { // Iteramos sobre los ornamentos
		if(example[ornaments[i]] < example[ornaments[i+1]]) { // Para la posición i, la actual, buscamos su valor dentro del objeto de ornamentos, si este es menor al siguiente...
    	sum.push(-Math.abs(example[ornaments[i]])) // ...lo agregamos al array como número negativo.
    } else {
    	sum.push(example[ornaments[i]]) // Caso contrario, lo pasamos al arreglo de manera normal.
    }
  }
  
 const result = sum.reduce((acc, item) => acc + item, 0) // Sumamos los números del array.
 console.log(result)
}

```

## Optimización y resultado
- El intento anterior cumplía con todos los casos menos con el caso en el cual recibimos un ornamento que no existe (`calculatePrice('#@Z')  // undefined (Z no tiene valor)`). Esta es la iteración:

```javascript
function calculatePrice(ornaments) {
  const prices = {
    '*': 1, 
    'o': 5,
    '^': 10,
    '#': 50,
    '@': 100
    }
 
  const priceSum = []
	
  for (let i = 0; i < ornaments.length; i++) {
		if(prices[ornaments[i]] < prices[ornaments[i+1]]) {
    	priceSum.push(-Math.abs(prices[ornaments[i]]))
    } else {
    	priceSum.push(prices[ornaments[i]])
    }
  }
 
  return priceSum.reduce((acc, item) => {
    if(isNaN(item)) {
      return undefined
    } else {
      return acc += item
      }
    }
    , 0)
}
```
## Enlaces y temas de interés
- [`Math.abs()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Math/abs): retorna valores absolutos de un número, en este caso nos permitió retornar el valor negativo.
- [`isNan()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/isNaN): arroja un booleano si el valor recibido es número o no.
- [Tutorial de claves de objetos en JavaScript](https://www.freecodecamp.org/espanol/news/tutorial-de-claves-de-objectos-en-javascript-como-usar-un-par-clave-valor-en-js/)
