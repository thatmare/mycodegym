# Is This a Triangle? 

[Is this a triangle?](https://www.codewars.com/kata/56606694ec01347ce800001b/train/javascript)

## Releer el problema

Implementar una función que acepte tres números. La función debe retornar true si con esos números se puede construir un triángulo, asumiendo que cada número corresponde a cada lado. Retornar false en cualquier otro caso. 

Todos los lados deben ser mayor a 0 para ser aceptados.

## Aproximación al problema

- Teorema de la desigualidad triangular: cualquier lado de un triángulo debe ser menor a la suma de sus otros dos lados. Es decir: a + b debe ser mayor que c, b + c debe ser mayor a a, c + a debe ser mayor a b. 
- Cada lado debe ser mayor a 0.

## Código

```
function isTriangle(a,b,c) {
  if( a + b <= c || b + c <= a || a + c <= b) {
    return false;
  } else if ( a == 0 || b == 0 || c == 0) {
    return false;
  } else {
    return true;
  }
}
```

## Recursos

- [Foro freeCodeCamp](https://forum.freecodecamp.org/t/is-this-a-triangle-help/281240/8)
- [Triangle Inequality Theorem](https://www.youtube.com/watch?v=NGHZVjYqA2s)
