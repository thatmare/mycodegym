# Cuenta de positivos y suma de negativos

## Releer el problema
[Codewars Count of Positives Sum of Negatives](https://www.codewars.com/kata/576bb71bbbcf0951d5000044/train/javascript)

Dado un arreglo (array) de números enteros, la función debe de regresar un nuevo arreglo con 1. La cuenta total de todos los números positivos y 2. La suma total de todos los números negativos. Si el arreglo recibido está vacío, el arreglo de resultado también debe estar vacío.

## Ejemplos

```
//Array recibido            //Array resultado
[1, 4, 6, 7, -20, -21, -5] -> [4, -46]
  [5, 7, 9, -30, -1, -5]   -> [3, -36]
```

## Aproximación

1. Hay que iterar el arreglo. Para esto, está la construcción `(let i = 0 ; i < input.length ; i++)` o `.forEach()`.
2. Hay que agregar una condicional por si el arreglo está vacío.
3. Hay que identificar los números si son negativos o positivos: para esto podemos compararlos con cero (si están después del cero = positivos, si están antes del 0 = negativos). Es decir: `i > 0, i < 0`
4. Hay que regresar el arreglo resultado con los dos nuevos valores. 

## Code

```
function countPositivesSumNegatives(input) {

  //Declaramos las variables en cero para poder agregarles valor.
  let positiveNum = 0;
  let negativeNum = 0;
  
  //Agregamos la condicional en dado caso de recibir un arreglo vacío.
  if (input == null || input.length == 0){
    return [];
  }
  
  //Usamos el método .forEach que sirve para iterar arreglos
  //La i indica cada posición del arreglo, es decir "para cada posición del arreglo input..."
  //? y : son sustituo para "if...else", es decir, si la condición a la izquierda de ? es true, se regresa el resultado a la derecha. De lo contrario, sucede el resultado enseguida de : 
    else {input.forEach((i) => i > 0 ? ++ positiveNum : negativeNum += i);
  }
  return [positiveNum, negativeNum];
}
```

## Test

![image](https://user-images.githubusercontent.com/113146161/227369476-76086cf4-fdca-4875-a050-36eed43c5b0c.png)

## Enlaces

- [Método .forEach( )](https://gomakethings.com/es6-foreach-loops-with-vanilla-javascript/)
- [Operadores ? y :](https://www.freecodecamp.org/news/how-the-question-mark-works-in-javascript/)
- [Solución por Christopher Nemeth](https://github.com/christopher-nemeth/codewars/blob/master/count-of-positives-sum-of-negatives.md)
- [Solución de codeManS](https://www.youtube.com/watch?v=N0tuLt7mhGI)
