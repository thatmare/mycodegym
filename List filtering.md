# List Filtering

[Codewars: List Filtering](https://www.codewars.com/kata/53dbd5315a3c69eed20002dd/train/javascript)

## Releer el problema

En este ejercicio vas a crear una función que reciba un arreglo con strings y números enteros no negativos, la cual retorna un nuevo arreglo solamente con los números filtrados. Es decir, solamente los valores de tipo numérico, no queremos números que son string.

## Ejemplos

```
filter_list([1,2,'a','b']) == [1,2]
filter_list([5, 'marissa', '1', '9', 8, 20]) == [5, 8, 20]

// Explicación

Entrada: [1,2,'a','b']
Salida: [1,2]
Explicación: De la entrada [1,2,'a','b'] se filtra el arreglo para unicamente
 tener los números positivos y retornar [1,2]
```

## Aproximación

- Utilizaremos el método `filter` para filtrar. Recordemos que este arreglo ya itera por sí solo.
- Utilizaremos el método `typeof` para identificar el tipo de dato numérico. 
- Utilizaremos el operador `===` para buscar igualdad estricta en el tipo de dato.

## Código

```
function filter_list(l) {
  //regresa el argumento l filtrado con la condición: para cada uno, vas a regresar cualquier item que su tipo de dato sea numérico
  return l.filter((item) => typeof item === 'number');
}
```
