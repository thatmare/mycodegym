# Codewars: You're a square!

[Codewars: You're a square](https://www.codewars.com/kata/54c27a33fb7da0db0100040e/train/typescript)

## Releer

Dado un número i, determinar si dicho número i es el producto de otro número al cuadrado. Se recibe un número y se retorna un booleano. 

## Ejemplos

```
-1  =>  false
 0  =>  true porque 0 x 0 = 0
 3  =>  false
 4  =>  true porque 2 x 2 = 4
25  =>  true porque 5 x 5 = 25
26  =>  false
```

## Aproximación

- ¿Cuál es la operación inversa a la potencia? La raíz cuadrada.
- Obtener la raíz cuadrada del número i con el método Math.sqrt()
- Si el resultado tiene decimales, retornar false
- Si el resultado no tiene decimales, retornar true
- Existe el método Number.isInteger() que retorna booleano dado un valor

## Código

```
export default function isSquare(n: number): boolean {
  return Number.isInteger(Math.sqrt(n));
};
```

## Alternativa

```
export default function isSquare(n: number): boolean {
  return Math.sqrt(n) % 1 == 0; // fix me
};
// Siendo i la raíz cuadrada de un número, si i dividido entre 1 tiene como residuo 0, retorna true; de lo contrario, false
```
