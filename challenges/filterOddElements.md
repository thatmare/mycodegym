# filterOddElements

## Releer

Escribe una función llamada "filterOddElements". Dado un array de números,"filterOddElements" devuelve un array que contiene sólo los números impares del array dado.
- El input es un array
- El output son números impares
- El output es un array
- Hay que insertar nuevos elementos después de la condición

## Ejemplos

[1, 2, 3, 4, 5] => [1, 3, 5]
[5, 6, 7, 8, 9] => [5, 7, 9]
[1, 3, 3, 2] => [1, 3, 3] 

## Aproximación

- Método filter ya itera
- Agregar la condición de impares:
- si hay residuo de la divisón de 2, entonces es impar

## Código

```
const filterOddElements = (arr) => {
  return arr.filter(n => n % 2 !== 0);
};
```

## Test

![image](https://github.com/thatmare/mycodegym/assets/113146161/aa3fff82-4e11-43d7-ba6a-2963ec93f0f6)
