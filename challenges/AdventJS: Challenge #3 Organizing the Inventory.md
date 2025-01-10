# AdventJS: Challenge #3 Organizing the Inventory 🪁🧸

[Reto: Organizing the inventory](https://adventjs.dev/challenges/2024/3)

Santa Claus está revisando el inventario de su taller para la entrega de regalos. Los elfos han registrado los juguetes en un array de objetos, pero la información está algo desorganizada. Tu trabajo es organizar el inventario. 

Recibirás un array de objetos, donde cada objeto representa un juguete y tiene los siguientes atributos:
- name: nombre del juguete (string)
- quantity: la cantidad disponible de dicho juguete (integer)
- category: la categoría a la cual pertenece el juguete (string)

Escribe una función que procese el array y retorne un único objeto que organice los juguetes en la siguiente estructura:

You will receive an array of objects, where each object represents a toy and has the properties:

- Las llaves de los objetos serán las categorías de los juguetes.
- Los valores de dichas llaves contienen otro objeto, con el nombre del juguete como llave y la cantidad disponible en cada juguete.
- Si hay juguetes dentro de la misma categoría, debes sumar las cantidades.
- Si el array está vacío, la función debe retornar un objeto solo.

## Releer el problema
- El input es un array de objetos con la siguiente estructura:
```
type Inventory = Array<
  { name: string, quantity: number, category: string }
>
```
- El output es un objeto: `object`
- Es necesario sumar la cantidad de juguetes duplicados

## Ejemplos

```
// Input
[
  { name: doll, quantity: 5, category: toys},
  { name: car, quantity: 2, category: toys},
  { name: ball, quantity: 3, category: sports},
  { name: doll, quantity: 1, category: toys}
]

// Output
{
  toys: {
    doll: 6,
    car: 2
  },
  sports: {
    ball: 3
  }
}

// Input
[]

// Output
{}
```

## Aproximación
- El método `reduce` nos va a permitir reducir todos los objetos del array entre un único array, y podemos hacer una comparación en el callback function.
- `reduce` va a acumular el resultado en un objeto.
- Dos criterios: además de filtrar por categoría, hay que "reducirlos" a una sola llave x juguete y su cantidad.

## Code

```
function organizeInventory(inventory) {
  return inventory.reduce((acc, item) => {
  // Si en el acumulador (acc) no se encuentra la categoría del valor actual (item),
  // dentro del objeto (acc, el acumulador), agrega la llave de la categoría y pon un objeto vacío
    if (!acc[item.category]) {
    console.log(acc)
      acc[item.category] = {};
    }
    // Para cada categoría, revisamos si el juguete ya está. Si es así, sumamos la cantidad al total que ya hay, 
    //si no, solo agregamos el dato
    if (acc[item.category][item.name]) {
      acc[item.category][item.name] += item.quantity;
    } else {
      acc[item.category][item.name] = item.quantity;
    }
    
      return acc;
    }, {});
}
```
