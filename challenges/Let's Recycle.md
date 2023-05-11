# Let's Recycle

[Codewars: Let's Recycle](https://www.codewars.com/kata/5b6db1acb118141f6b000060/train/javascript)

## Releer

Se te dará una lista de objetos. Cada objeto tiene type, material y posiblemente secondMaterial. Los materiales existentes son: paper, glass, organic, y plastic. Tu trabajo es clasificar estos objetos en los 4 contenedores de reciclaje de acuerdo con su material (y secondMaterial, en caso de existir), listando el valor type de los objetos que deben ir en esos contenedores.

Notas

- Los contenedores deben venir en el mismo orden que los materiales enumerados anteriormente. (paper, glass, organic, y plastic).
- Todos los contenedores deben aparecer en la salida, incluso si algunos de ellos están vacíos,
- Si un objeto está hecho de dos materiales, type debe aparecer en los dos contenedores respectivos.
- El orden de los type's en cada contenedor debe ser el mismo que el orden de sus respectivos objetos en la lista de entrada.

## Ejemplos

```
entrada = [
  {"type": "rotten apples", "material": "organic"},
  {"type": "out of date yogurt", "material": "organic", "secondMaterial": "plastic"},
  {"type": "wine bottle", "material": "glass", "secondMaterial": "paper"},
  {"type": "amazon box", "material": "paper"},
  {"type": "beer bottle", "material": "glass", "secondMaterial": "paper"}
]
salida = [
  ["wine bottle", "amazon box", "beer bottle"], // PAPER: secondMaterial, paper, secondMaterial
  ["wine bottle", "beer bottle"], // GLASS: material, material
  ["rotten apples", "out of date yogurt"], // ORGANIC: material, material
  ["out of date yogurt"] // PLASTIC: plastic
]
```

## Aproximación

- La salida es un array de objetos: método map
- Método filter para filtrar por su key.
- Validación para que sea o por el material o por el segundo material

## Código
```
const materials = ['paper', 'glass', 'organic', 'plastic'];

function recycle(array) {
    return materials.map((material) => array.filter((object) => object.material == material || object.secondMaterial == material).map((o) => o.type));
}


EXPLAIN
// Almacenar los materiales de reciclaje en una constante
const materials = ['paper', 'glass', 'organic', 'plastic'];

// Recibe como parámetro el array de objetos
function recycle(array) {
    // Regresar el array de materiales mapeado... para cada material...
    return materials.map((material) => 
    // Vas a filtrar el array con la condición...
    array.filter((object) => 
    // de que la clave material o secondMaterial del objeto coincide con material
    object.material == material || object.secondMaterial == material)
    // Esta filtración, la vas a mapear (para regresar los array) y vas a devolver el objeto de acuerdo con su valor en su clave "type"
    .map((o) => o.type));
}

```

## Test

![image](https://github.com/thatmare/mycodegym/assets/113146161/268662b7-bf4d-4401-8bcb-698ad09d19f8)

![image](https://github.com/thatmare/mycodegym/assets/113146161/56f30ec0-5222-4201-9b72-6c2fc7da6e20)


## Optimizar

Otra alternativa:

```
function recycle(arr) {
  let paper = [], glass = [], organic = [], plastic = [];

  arr.forEach(obj => {  
    if(obj.material === 'paper' || obj.secondMaterial === 'paper' ) paper.push(obj.type)
    if(obj.material === 'glass' || obj.secondMaterial === 'glass') glass.push(obj.type)
    if(obj.material === 'organic' || obj.secondMaterial === 'organic') organic.push(obj.type)
    if(obj.material === 'plastic' || obj.secondMaterial === 'plastic') plastic.push(obj.type)
  });

  return [paper, glass, organic, plastic]
}
```
