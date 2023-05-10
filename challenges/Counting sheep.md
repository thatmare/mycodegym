# Counting Sheep

[Code Wars: Counting Sheep](https://www.codewars.com/kata/54edbc7200b811e956000556/train/javascript)

## Releer

Considera un array de valores true o false. Necesitamos una función que cuente la cantidad de veces que está presente el valor de true. Considera que puede haber otros valores como null y undefined.

## Ejemplos

```
[true, true, true, false] => 3
[true, false, false, false] => 1
[false, true, false, true] => 2
```

## Aproximación
- Método reduce: recuerda que necesita de dos parámetros (el acumulador y el valor siguiente) y el valor inicial al final. 
- Validar si el valor siguiente es === true. 
- ¿Usar operador ternario?

## Código

```
function countSheeps(arrayOfSheep) {
  return arrayOfSheep.reduce((a, b) => b === true ? a + 1: a, 0);
}
```

## Test

![image](https://github.com/thatmare/mycodegym/assets/113146161/d1af5b71-542a-458d-b7b7-8c4ddaee3be7)

## Optimizar
Otra alternativa:
```
function countSheeps(arrayOfSheep) {
    const result = arrayOfSheep.filter((a) => a === true);
    return result.length;
}
```
