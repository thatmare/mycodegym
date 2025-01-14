# Reto #5 👞 Emparejando los zapatos

[Reto #5 👞 Emparejando los zapatos](https://adventjs.dev/en/challenges/2024/5)

Santa Claus's elves 🧝🧝‍♂️ have found a bunch of mismatched magic boots in the workshop. Each boot is described by two values:

type indicates if it's a left boot (I) or a right boot (R).
size indicates the size of the boot.
Your task is to help the elves pair all the boots of the same size having a left and a right one. To do this, you should return a list of the available boots after pairing them.

Note: You can have more than one pair of boots of the same size!

```javascript
const shoes = [
  { type: 'I', size: 38 },
  { type: 'R', size: 38 },
  { type: 'R', size: 42 },
  { type: 'I', size: 41 },
  { type: 'I', size: 42 }
]

organizeShoes(shoes)
// [38, 42]

const shoes2 = [
  { type: 'I', size: 38 },
  { type: 'R', size: 38 },
  { type: 'I', size: 38 },
  { type: 'I', size: 38 },
  { type: 'R', size: 38 }
]
// [38, 38]

const shoes3 = [
  { type: 'I', size: 38 },
  { type: 'R', size: 36 },
  { type: 'R', size: 42 },
  { type: 'I', size: 41 },
  { type: 'I', size: 43 }
]

organizeShoes(shoes3)
// []
```

## Releer el problema
Los elfos de Santa tienen zapatos desordenados. Cada zapato tiene dos características: su tipo, `type`, que indica si es derecha (`R`), o izquierda (`I`); y su talla, `size`, que indica la talla del zapato. 

Tu trabajo es emparejar todos los zapatos por su talla, y considerando que tenga su derecha e izquierda. Puede haber más de un par de la misma talla. 

```typescript
// tipo Shoe, un objeto con llave "type" que puede tener valor string "I" o "R", y llave "size" que puede tener valor número
type Shoe = {
  type: 'I' | 'R'
  size: number
}

// parámetros: array de objetos tipo Shoe
// valor de retorno: array de números
function organizeShoes(shoes: Shoe[]): number[] {
  return []
}
```

## Ejemplos
```javascript
const shoes = [
  { type: 'R', size: 42 },
  { type: 'I', size: 42 }
]

organizeShoes(shoes)
// [42]

const shoes2 = [
  { type: 'I', size: 38 },
  { type: 'R', size: 38 },
  { type: 'I', size: 40 },
  { type: 'I', size: 40 },
]
// [38]

const shoes3 = [
  { type: 'R', size: 42 },
  { type: 'I', size: 41 },
  { type: 'I', size: 43 }
]

organizeShoes(shoes3)
// []
```

## Aproximación
1. Agrupar por su tipo de zapato
  - Vamos a iterar sobre el array para almacenar **las tallas de los zapatos** en un único objeto con dos valores, uno de izquierda y otro de derecha. 
2. 
4. Comparar tallas (array de números)
5. Buscar coincidencias

## Código
```javascript
function organizeShoes(shoes) {
	const pairs = shoes.reduce((acc, item) => {
 		if(!acc[item.type]) { // si no existe la llave "I" o "R"...
    	acc[item.type] = [] // agregarla y asignarle un array vacío 
    }
    
    acc[item.type].push(item.size) // para la llave, agregar sus tallas
    
    return acc
  }, {}) // el acumulador es un objeto
  
  const left = pairs.I // array de tallas de zapatos izquierdos
  const right = pairs.R // array de tallas de zapatos derechos
 
	const matchedPairs = []; // array vacío para almacenar coincidencias
  
  for (const size of left) { // Iterar sobre el array de izquierdos...
    const index = right.indexOf(size); // dentro del array de derechos, encontrar el índice de la talla del izquierdo.
    if (index !== -1) { // Si el índice no se encuentra...
      matchedPairs.push(size); // agregarlo.
     
    }
  }
  
  return matchedPairs;
}
```

## Temas y enlaces de interés
