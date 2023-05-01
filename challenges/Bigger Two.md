# Bigger Two

[Bigger Two](https://the-winter.github.io/codingjs/exercise.html?name=biggerTwo&title=Array-1)

## Releer problema

Se tienen dos arreglos de números enteros, a y b, cada uno de longitud dos. Calcule la suma de los valores de cada arreglo. Devuelva el array que tenga la mayor suma. En caso de empate, devuelva el arreglo a.

## Ejemplos

```

biggerTwo([2, 3],[5, 6]) -> [5, 6]
biggerTwo([5, 6],[1, 2]) -> [5, 6]
biggerTwo([5, 6],[5, 6]) -> [5, 6]
biggerTwo([1, 2],[1, 1]) -> [1, 2]
biggerTwo([1, 2],[1, 2]) -> [1, 2]

```

## Aproximación
- Comparar los arrays (>, <)
- Considerar todos los escenarios (si es mayor la suma de a, si es mayor la suma de b, si es un empate)
- Utilizar `return` para el arreglo resultante de cada escenario

## Código

```
function biggerTwo(a, b){
//Si la suma del index 0 y del index 1 del arreglo a es mayor que la suma del index 0 y del index 1 del arreglo b...
  if (a[0] + a[1] > b[0] + b[1]) {
  //regresar el array a
  return a
  //En cambio, si la suma del index 0 y del index 1 del arreglo a es menor que la suma del index 0 y del index 1 del arreglo b...
  } else if (a[0] + a[1] < b[0] + b[1]) {
  //regresar el array b
  return b
  //en cualquier otro caso regresar el array a
  } else {
    return a
  }
}
```

## Test

![image](https://user-images.githubusercontent.com/113146161/232935144-190f1af3-dfd9-4b81-a4b9-91e17e27bb92.png)
