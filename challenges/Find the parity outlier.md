#

## Releer

You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer N. Write a method that takes the array as an argument and returns this "outlier" N.
- El array o está compuesto de números pares o impares, pero hay uno que no encaja en estas categorías.
- La función debe de identificar este número que no encaja, independientemente si es un array de impares o pares

## Ejemplos

```
[2, 4, 6, 10, 11, 20] => 11 es num odd
[1, 3, 5, 7, 9, 12] => 12 es num even
```

## Aproximación
- Condición para identificar pares: n % 2 == 0
- Condición para identificar imapres: n % 2 != 0
- Iterar para buscar en el array
- El input es un array
- El output es un elemento del array
- Condicional dentro de la condicional??: si los demás elementos del array son pares, encontrar el impar ; si los demás elementos del array son impares, encontrar los pares

## Código
## Test
## Optimizar
