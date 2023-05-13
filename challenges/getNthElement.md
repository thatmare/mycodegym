# getNthElement

[getNthElement](https://curriculum.laboratoria.la/es/topics/javascript/arrays/practice/get-nth-element)

## Releer
Escribe una función llamada getNthElement.
Dado un arreglo y un entero, getNthElement devuelve el valor según el entero dado, dentro del arreglo dado.

Notas:
Si el arreglo tiene una longitud de 0, debería devolver' undefined'.

- Siempre recibiremos un array un entero. Esos son valores de input. 
- El entero dicta el index dentro del array.

## Ejemplo
```
([1, 2, 3, 4], 2) => 3
([6, 8, 3], 1) => 8
([4, 5, 4], 2) => 4
```

## Aproximación
- El entero fuera del array debe de designarse como index/position del array
- ¿Puede almacenarse ese num en una variable que va a dictar el index?
- Recuperar el elemento de n index.
- ¿Cómo recuperar un elemento de array? => solo con la sintaxis de corchetes se indica la posición.

## Código

```
const getNthElement = (array, n) => {
  return array[n];
};
```

## Test

![image](https://github.com/thatmare/mycodegym/assets/113146161/24dfb74c-d660-430d-a2f8-e5ce60c21853)

## Optimizar
