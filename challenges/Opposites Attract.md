# Opposites Attract

## Releer el problema

Timmy y Sarah creen estar enamorados, pero solo lo sabrán hasta que cada uno escoja una flor del jardín. Si una de las flores tiene un número par de pétalos y la otra tiene un número impar, significa que están enamorados. 

Escibre una función que tome el número de pétalos de cada flor y retorne `true` si están enamorados y `false` si no están enamorados. 

## Ejemplos

```
lovefunc(1,2) => true
lovefunc(3,6) => true
lovefunc(1,1) => false
lovefunc(2,2) => false
lovefunc(2,1) => true
```

## Aproximación

- if (num par && num impar) {return true} else {return false}
- flower1 % 2 = 0
- Si el residuo de la divisón de flower1 o de flower2 entre 2 es 0, entonces es un número par
- Si hay residuo en la división de flower1 o de flower2 entre 2, entonces es un número impar

## Code

```
function lovefunc(flower1, flower2){
  if(flower1 % 2 == 0 && flower2 % 2 == 1 || 
     flower1 % 2 == 1 && flower2 % 2 == 0) {
  return true;
  } else {
    return false;
  }
}
```

## Optimizar

```
function lovefunc(flower1, flower2){
  return ((flower1%2==0 && flower2%2!=0) || (flower1%2!=0 && flower2%2==0)) ? true : false;
}
```
