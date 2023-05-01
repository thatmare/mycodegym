# Abbreviate a Two Word Name

[Abbreviate a Two Word Name](https://www.codewars.com/kata/57eadb7ecd143f4c9c0000a3/train/javascript)

## Releer el problema

Escribe una función que convierte un nombre en iniciales. Esta función toma exactamente dos palabras con un espacio entre ellos. La salida debe ser dos letras capitalizadas con un punto que las separa.

## Ejemplos

```
Marissa Vargas -> M.V
marissa vargas -> M.V
```

## Aproximación

- No importa si las letras están capitalizadas, debemos usar el método `.toUpperCase`
- Unir con un . con `.join`
- Separar las dos palabras para con cada una recuperar la primera y capitalizar

## Código

```
function abbreviateName(name) {
  return (
    name
      //Separa la cadena de texto donde está el espacio
      .split(" ")

      //De cada palabra, toma el primer caracter (index 0) y pásalo a mayúscula
      .map((character) => character[0].toUpperCase())

      //Une con un punto
      .join(".")
  );
}
```
