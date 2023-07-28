# Good Array

## Releer 
Dado un array de elementos string, devuelve un string que no repita caracteres consecutivamente.
- Input es un array.
- Output es un string.
- Si dos elementos consecutivos son iguales, se elimina uno de ellos.

## Ejemplos
```
['a', 'b', 'b'] => 'ab'
['a', 'b', 'a'] => 'aba'
['b', 'b'] => 'b'
```

## Aproximación
- El método reduce nos sirve para:
   - tomar dos elementos dos consecutivos y, dada una condición, compararlos
   - acumular y concatenar
- Al final, concatenar con join
- En este ejercicio, el método slice nos sirve para transformar el elemento acumulador en un array
- "Del array, toma un acumulador y un elemento actual: vas a acumularlo en un array con la siguiente condición: dado el primer elemento acumulador, si es igual al segundo, solo retorna el primero; de lo contraro, retorna en un array el primero y el segundo".

## Código
```
function goodArray(arr: string[]): string {
	const noRepeat = arr.reduce((first, second) => first.slice(-1)[0] === second ? first : [...first, second], [])
  return noRepeat.join('')
}
```

