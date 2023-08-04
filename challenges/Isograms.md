# Isogram

Un isograma es una palabra que no repite letras, sean o no sean consecutivas. Hay que crear una función que reciba un string y arroje un booleano, true si la palabra es un isograma y false si no lo es. Una cadena vacía es un isograma. Ignora capitalización.

## Releer

- Vamos a recibir una cadena de texto.
- Si una letra está presente en la palabra, para que sea un isograma, esta letra no debe repetirse.
- No importa si son continuas o no.
- Vamos a arrojar true o false.

## Ejemplo

```
"Ejemplo" => false
"wildest" => true
"dream" => true
"cardigan" => false
"moOse" => false
"rain" => true
```

## Aproximación
- Hacer split a la cadena de texto. Esto arrojará un array.
- Ordenar los elementos de array con sort. Esto arrojará los elementos ordenados alfabéticamente.
- Una vez ordenados, podríamos utilizar reduce para identificar si se repiten o no.
- "Si elemento a es igual a elemento b remueve el siguiente elemento"
- Unimos las letras resultantes de la eliminación
- Comparamos la longitud de las palabras
- Si la longitud es la misma, true, si es distinta, false

## Código

```
export function isIsogram(str: string): boolean{
  const sortArr = str.toLowerCase().split("").sort();
  
  const noRepeat = sortArr.reduce((a: string[], b: string) => a.slice(-1)[0] === b ? a : [...a, b], []);
  
  const newWord = noRepeat.join('');
  
  if(newWord.length !== str.length) {
  	return false
  } else {
    return true
  }
}
```

## Optimizar

```
export function isIsogram(str: string): boolean {
  const sortArr = str.toLowerCase().split("").sort();

  const noRepeat = sortArr.reduce((a: string[], b: string) => a.slice(-1)[0] === b ? a : [...a, b], []);

  const newWord = noRepeat.join('');

  return newWord.length === str.length;
}

=========================================

export function isIsogram (str: string): boolean {
  return (new Set(str.toLowerCase())).size === str.length
}
```
