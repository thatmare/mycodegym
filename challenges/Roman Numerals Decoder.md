# Roman Numerals Decoder

## Releer

Convierte números romanos a su valor decimal. 
- Input: string
- Output: números

## Ejemplos

```
['XXI'] => 21
['VII'] => 8
['MMXXIII'] => 2023
```

## Aproximación

- Utilizar objetos: al asignar una key con comillas, puede equivaler tanto al valor de esa key como a un string.
- Iterar sobre el objeto con el bucle for.
- Tomar en cuenta el sistema romano: se suma de derecha a izquierda.

## Código

```
function solution(roman) {
  const romanNums = { // objeto
    'I': 1,
    'V': 5,
    'X': 10,
    'L': 50,
    'C': 100,
    'D': 500,
    'M': 1000
  }

  let total = 0; // inicializamos el total en 0 para poder agregarle los valores
  let prevValue = 0; // tomaremos en cuenta el valor anterior, mientras es 0

  // bucle for: iteramos sobre el string de input. Queremos empezar a iterar desde el último caracter, así que tomamos la longitud de la cadena -1. 
  // la iteración continúa mientras i sea igual o mayor a 0
  // la i tiene decremento para que recorra hacia la izquierda
  for (let i = roman.length - 1; i >= 0; i--) {
    let numeral = roman[i]; // numeral es igual al input en el index i
    let value = romanNums[numeral]; // el valor es igual al objeto en el index del numeral (recordemos: ya que los keys son string y nuestro input es string, va a recuperar el valor del mismo)

    if (value < prevValue) { // si el valor actual es menor a 
      total -= value;
    } else {
      total += value;
      prevValue = value;
    }
  }

  return total;
}

console.log(solution('XXI')); // Output: 21

```

## Tests
