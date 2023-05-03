# Lost Without a Map
[Codewars: Lost Without a Map](https://www.codewars.com/kata/57f781872e3d8ca2a000007e/train/javascript)

## Releer
Dado un array de números devuelve un nuevo array que duplique el valor de cada elemento/número del array original.

## Ejemplos

```
[1,2,3] => [2,4,6]
[4,5,6] => [8,10,12]
[1,1,1] => [2,2,2]
```

## Aproximación

- Para iterar: forEach, map.
- Duplicar: *2

## Código

```
function maps(x){
  return x.map((number) => number * 2);
};
```

## Test

![image](https://user-images.githubusercontent.com/113146161/236072742-e966a46d-3c31-4e14-8504-89b08bdcd612.png)

## Optimizar
```
function newMaps(x) {
    return x.map(number => number * 2)
}
```
