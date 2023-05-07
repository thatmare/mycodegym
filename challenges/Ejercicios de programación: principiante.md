# [Ejercicios de programación: principiante](https://hub.hybridge.education/share/c2324031-cbb3-4f01-b74c-e9e3c05158bf#h-facil)
## 1. Instrucción

1. Crea una variable y almacena tu nombre
2. Crea una variable y almacena tu apellido paterno
3. Crea una variable y almacena tu apellido materno
4. Concatena las tres variables anteriores en una sola que se llame nombreCompleto

## Solución
```
const name = "Marissa";
const lastName = "Vargas";
const secondLastName = "Sánchez";

let nombreCompleto = name + " " + lastName + " " + secondLastName; 
console.log(nombreCompleto) => 'Marissa Vargas Sánchez'
```

## 2. Instrucción

1. Crea cuantas variables quieras de tipo string y asigna el nombre de un amigo tuyo a cada variable
2. Inserta (adjunta) estas variables a una nueva lista que se llame "amigos”
3. Imprime un mensaje que indique al usuario cuántos elementos contiene la lista de amigos, ej. "La lista de amigos tiene X elementos”, X siendo la cantidad de elementos. Se debe usar la función len()
4. Imprime el primer elemento de la lista de amigos todo en mayúsculas utilizando funciones de strings de Python
5. Almacena en una variable el valor del tercer caracter del segundo elemento de tu lista de amigos e imprímela.

## Solución

```
const amigas = [];
const amiga1 = "Marissa";
const amiga2 = "Diana";
const amiga3 = "Carolina";

amigas.push(amiga1, amiga2, amiga3);
console.log(amigas); =>  (3) ['Marissa', 'Diana', 'Carolina']

function len(arr) {
    return "La lista de amigos tiene " + (amigas.length) + " elementos."
}

len(amigas); => 'La lista de amigas tiene 3 elementos.'

amigas[0].toUpperCase(); => 'MARISSA'

let thirdChar = amigas[1].slice(2,3);
console.log(thirdChar); => a
```

## 3. Instrucción 
1. Crea una lista que contenga 5 números aleatorios
2. En una sola línea de código, imprime el resultado de la suma de estos 5 números
3. Agrega tres números nuevos a la lista de números
4. En una sola línea de código, imprime el resultado de la multiplicación de estos 5 números

## Solución
```
const nums = [1, 2, 3, 4, 5];

nums.reduce((total, next) => total + next); => 15

nums.push(6, 7, 8);
console.log(nums); => (8) [1, 2, 3, 4, 5, 6, 7, 8]

nums.reduce((total, next) => total * next); => 40320
```

## 4. Instrucción

1. Crea una constante para almacenar un número.
2. Usa condicionales para saber si el número es positivo, negativo o cero.
3. Prueba con diferentes números.

## Solución

```
let num = 12;

function positiveOrNegative(n) {
    if(n === 0) {
        return "El número es cero.";
    } else if(n >= 0) {
        return "El número " + n + " es positivo.";
    } else if(n <= 0) {
        return "El número " + n + " es negativo.";
    }
}

positiveOrNegative(num); => "El número 12 es positivo."
num = -1;
positiveOrNegative(num) => 'El número -1 es negativo.'
num = 0 
positiveOrNegative(num) => 'El número es cero.'
```
