# front22

[The Winter: front22](https://the-winter.github.io/codingjs/exercise.html?name=front22&title=Warmup-1)

## Releer

Dada una cadena de texto, tomar los primeros dos caracteres y concaternarlos al principio y al final de la cadena misma. 

## Ejemplos

```
front22('kitten') → kikittenki
front22('Ha') → HaHaHa
front22('abc') → ababcab
```

## Aproximación

- Se puede acceder al caracter de una cadena de texto con la destructuración: str[0].
- Se puede concatenar con el método concat.
- Se puede concatenar con el operador +.
- Hay que corroborar la longitud de la cadena de texto.
- De ser '', se retorna ''.
- De ser 'a', se retorna 'aaa'.

## Código

```
function front22(str){
  const empty = '';
  if(str.length === 0) {
    return '';
  } else if (str.length === 1){
    return empty.concat(str[0], str, str[0])
  } else {
    return empty.concat(str[0], str[1], str, str[0], str[1])
  }
}
```

## Optimizar

```
function front22(str){
  const chars = str.slice(0,2);
  return chars + str + chars;
}
```
