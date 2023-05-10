# Odd or Even

## Releer

Tu objetivo en este ejercicio es implementar una función que recibe un arreglo con números enteros y determinar si la suma de los números es par o impar. De acuerdo al resultado de la suma deberás retornar una cadena en caso de que sea par 'odd' y en el caso de que sea impar 'even'. Si el arreglo está vacío toma el arreglo como [0].

## Ejemplos

[1, 2, 3, 4] => 'even'
[0, 5, 6] => 'odd'
[-1, -7] => 'even'

## Aproximación

- Primero, hay que sumar: método reduce. Recuerda: dos parámetros y marcar el valor inicial. 
- Validación de si es par o impar: % 2, si no hay residuo entonces es par, si hay residuo entonces es impar.
- return odd / return even

## Código

```
function oddOrEven(array) {
   const sum = array.reduce((a, b) => a + b, 0);
    if(sum % 2 === 0) {
        return 'odd';
    } else if (sum % 2 !== 0) {
        return 'even';
    }
};
```

## Test

![image](https://github.com/thatmare/mycodegym/assets/113146161/0ef3b124-c479-478a-badd-96b7858f72fa)


## Optimizar

```
function oddOrEven(array) {
   const sum = array.reduce((a, b) => a + b, 0);
    
  return sum % 2 === 0 ? 'even' : 'odd';
};
```
