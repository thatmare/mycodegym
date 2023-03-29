# Codewars: Sum Arrays

[Codewars: Sum Arrays](https://www.codewars.com/kata/53dc54212259ed3d4f00071c/train/javascript)

## Releer problema

Crear una función que devuelva la suma de los números dentro del arreglo. Los números pueden ser negativos o con decimal. Si no hay nada dentro del array, debe de regresar 0. 

## Ejemplos

```
[1, 2, 3, 4, 5] => [15]
[1, -2, 3] => [2]
[-2.5, -4, 1] => [5.5]
[-5, 7, 4.2] => [6.2]
```

## Aproximación

- Agregar una condicional por si el arreglo está vacío: if (numbers.length === 0) return 0
- Hay que recorrer o iterar el arreglo.
- El método reduce es un método para sumar valores dentro de un arreglo:
  * `reduce()` recibe dos parámetros: el primer parámetro será el número en la primera posición; el segundo parámetro será el número enseguida del de la primera posición (es decir, el de la derecha).
  * Estos dos números se suman: entonces, el método comienza a iterar, así que ese total de suma va a agregar el número enseguida de su posición (el siguiente de la derecha.
  * Esto se repite hasta terminar de recorrer el arreglo y entonces retorna el valor total. 

## Code

```
function sum (numbers) {
    "use strict";
    if (numbers.length === 0)
    return 0;
    numbers.reduce((total, amount) => total + amount);
    
};
```

## Test

![image](https://user-images.githubusercontent.com/113146161/228669375-ec6de239-1ef7-4e5b-814f-a0196134977e.png)

![image](https://user-images.githubusercontent.com/113146161/228669432-2c9b6aab-0c5f-4410-bf07-c7488e01356f.png)

## Optimizar

```
function sum (numbers) {
    "use strict";
    if (numbers.length === 0) {
        return 0
    }
    else { 
        return numbers.reduce((total, amount) => total + amount)
    }
}
```

## Enlaces

[A Guide to the Reduce Method in JavaScript](https://www.freecodecamp.org/news/reduce-f47a7da511a9/)
