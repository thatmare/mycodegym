# Moving Zeros to End

## Releer el problema

Escribir una función que reciba un arreglo con elementos de todo tipo de datos (numéricos, strings, booleanos...) y regrese un array con todos los 0 al final, sin alterar la posición de los otros elementos del array. 

## Ejemplos

```
[false,1,0,1,2,0,1,3,"a"] -> [false,1,1,2,1,3,"a", 0, 0]
[0, 0, "m", true, "a", 0, 5, 8] -> ["m", true, "a", 5, 8, 0, 0, 0]
```

## Aproximación

- Iterar sobre el arreglo para identificar aquellos elementos que sean número 0. 
- Método para desplazar esos elementos indicándole la posición hacia el final de array. 
- El método push inserta elementos al final de array. 

## Código

