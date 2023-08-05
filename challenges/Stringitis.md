# Stringitis

Escribe una función que tome un texto y un subtexto y devuelva true si el texto contiene el subtexto y false en caso contrario.

## Releer

Recibiremos una cadena de texto.
Retornaremos un booleano.
No menciona nada de capitalización.
Es independiente de la posición de toda la cadena.
Depende de que coincidan los caracteres y su orden.

## Ejemplos

```
hasText('Laboratoria', 'oratoria');
// true

hasText('Equipo', 'yo');
// false

hasText('hola', 'ola')
// true

hasText('Lluvia', 'via')
// true
```

## Aproximación

- El método substring nos devuelve una subcadena de texto. Puede recibir un índice o dos, uno de inicio y otro de fin.
- Si pasamos una variable i que venga de loop, arrojará substring por cada index de la cadena.
- Esos substrings los arrojamos en un array.
- El array lo filtramos con la condición de que haya coincidencia con el segundo argumento.
- Si la longitud del array es 0, retorna false.

## Código

```
function hasText(text, subtext) {
	let array = [];
  
  for(let i = 0; i < text.length; i++) {
  	array.push(text.substring(i))
  };
  
  const result = array.filter(a => a === subtext);
  
  return result.length !== 0;
}
```
## Optimizar

```
function hasText(text, subtext) {
	let array = [];
  
  for(let i = 0; i < text.length; i++) {
  	array.push(text.substring(i))
  };
  
 return array.includes(subtext);
}

================================================

function hasText(text, subtexto) {
  return text.indexOf(subtexto) !== -1;
}


```
