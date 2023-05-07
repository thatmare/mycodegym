# [Ejercicios de programación: intermedio](https://hub.hybridge.education/share/c2324031-cbb3-4f01-b74c-e9e3c05158bf#h-intermedio)

## 1. Instrucción

1. Crea una variable llamada year para almacenar un año, luego escribe un programa que verifique si el año es bisiesto o no. Estas son las regla de decisión:
2. El número es divisible por 400.
3. El número es múltiplo de 4 y no es múltiplo de 100.

```
Año: 2020
Sí es año bisiesto
```

## Solución
```
let year = 1584;

function leapYear(y) {
    if((y % 400 == 0) || (y % 4 == 0 && y % 100 !== 0)) {
        return "El año " + y + " es bisiesto." 
    } else {
        return "El año " + y + " no es año bisiesto."
    }
} 

leapYear(year);
'El año 1584 es bisiesto.'
```
### Optimización:

```
function leapYear(y) {
  return (y % 400 === 0 || (y % 4 === 0 && y % 100 !== 0)) ? `El año ${y} es bisiesto.` : `El año ${y} no es bisiesto.`;
}

year = 2022;

leapYear(year);
'El año 2022 no es bisiesto.'
```
## 2. Instrucción

1. Escribe un programa que imprima los números del 1 al 100. Pero:
2. Para los múltiplos de 3, imprime "Fizz" en lugar del número.
3. Para los múltiplos de 5, imprime "Buzz" en lugar del número y
4. Para los múltiplos tanto de 3 y de 5, imprime "Fizz-Buzz".

```
1
2
Fizz
4
Buzz
.
.
.
14
Fizz-Buzz
16
.
.
.
```

## Solución

```
let oneToHundred = new Array(100);

for (let i = 0; i < 100; i++){
    oneToHundred.push[i];
}

oneToHundred => (100) [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100]

function fizzBuzz(arr) {
  arr.forEach((n, i) => {
    if (n % 15 === 0) {
      arr[i] = "Fizz-Buzz";
    } else if (n % 3 === 0) {
      arr[i] = "Fizz";
    } else if (n % 5 === 0) {
      arr[i] = "Buzz";
    }
  });
}

fizzBuzz(oneToHundred); => (100) [1, 2, 'Fizz', 4, 'Buzz', 'Fizz', 7, 8, 'Fizz', 'Buzz', 11, 'Fizz', 13, 14, 'Fizz-Buzz', 16, 17, 'Fizz', 19, 'Buzz', 'Fizz', 22, 23, 'Fizz', 'Buzz', 26, 'Fizz', 28, 29, 'Fizz-Buzz', 31, 32, 'Fizz', 34, 'Buzz', 'Fizz', 37, 38, 'Fizz', 'Buzz', 41, 'Fizz', 43, 44, 'Fizz-Buzz', 46, 47, 'Fizz', 49, 'Buzz', 'Fizz', 52, 53, 'Fizz', 'Buzz', 56, 'Fizz', 58, 59, 'Fizz-Buzz', 61, 62, 'Fizz', 64, 'Buzz', 'Fizz', 67, 68, 'Fizz', 'Buzz', 71, 'Fizz', 73, 74, 'Fizz-Buzz', 76, 77, 'Fizz', 79, 'Buzz', 'Fizz', 82, 83, 'Fizz', 'Buzz', 86, 'Fizz', 88, 89, 'Fizz-Buzz', 91, 92, 'Fizz', 94, 'Buzz', 'Fizz', 97, 98, 'Fizz', 'Buzz']

```
## 3. Instrucción

Crea una constante year en la que guardarás un año, luego imprime el siglo en el que se encuentra. Recuerda que el primer siglo va desde el año 1 hasta, incluyendo, el 100.

```
Año: 1905
Siglo: 20
```

## Solución

```
let year = 2020; 

function century(y){
    return Math.ceil(y / 100)
}

century(year); => 21
```

## 4. Instrucción

Guarda en una constante n el alto de una escalera. Imprime la escalera de n niveles en la consola. Por ejemplo, con n = 4 obtenemos:
```
   #
  ##
 ###
####
```
## Solución
```
const n = 4; // Altura de la escalera

for (let i = 1; i <= n; i++) {
  const spaces = ' '.repeat(n - i);
  const hashtags = '#'.repeat(i);
  const stair = spaces + hashtags;
  console.log(stair);
}

```

# Recursos
- [Repeat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat)
- [Math.ceil, Math.floor, Math.round](https://www.educative.io/answers/mathceil-mathfloor-and-mathround-in-javascript)
- [Populate an array](https://stackoverflow.com/questions/33544993/i-want-to-print-1-to-100-numbers-using-arrays-in-javascript-only)
