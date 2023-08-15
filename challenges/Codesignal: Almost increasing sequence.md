# Codesignal: Almost increasing sequence

Given a sequence of integers as an array, determine whether it is possible to obtain a strictly increasing sequence by removing no more than one element from the array.
[Challenge](https://app.codesignal.com/arcade/intro/level-2/2mxbGwLzvkTCKAJMG)

## Releer

- Recibiremos un array de números enteros.
- El valor de retorno debe ser un booleano.
- Puede que los números del array no estén ordenados secuencialmente.
- La idea es que encontremos si es posible crear un orden secuencial de incremento al quitar un elemento del array.
- Independientemente de si son números consecutivos o no.
- No cambiaremos la posición de ningún elemento.

## Ejemplo

```
[1, 2, 3, 5, 4] => true, al eliminar el 4
[8, 9, 6, 76, 1] => false, porque para lograr el orden secuencial deberíamos quitar o el 6 o el 1
[10, 20, 44, 6, 23] => false, porque para lograr el orden secuencial deberíamos quitar el 6 o 23
```

## Aproximación

// tomemos array original vs array comparado
// si la posición de los elementos de los array cambia en más de una arrojar false
// de lo contrario arrojar true

## Código

## Optimizar
