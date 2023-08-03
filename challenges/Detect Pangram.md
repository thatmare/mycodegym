# Detect Pangran
Dada una oración, retorna true o false dependiendo si la oración es un pangrama. Un pangrama es aquella oración que tiene todas las letras del alfabeto por lo menos una vez. 

## Releer el problema
- Vamos a recibir una cadena de texto.
- Debemos retornar un booleano.
- La ocurrencia de las letras del alfabeto debe ser por lo menos una
- No importa si hay repetición
- No importa la capitalización
- Ignorar caracteres especiales, menos el punto

## Ejemplos
```
"The quick brown fox jumps over the lazy dog" => true
"This is not a pangram" => false
```

## Aproximación
- Podríamos crear un array u objeto e iterar en él para saber si hay coincidencia en la cadena de texto.
- Utilizar una expresión regular
- Utilizar el método match: el método match nos arroja un array
- Si la longitud del array es de 26 (longitud del abecedario) arrojar true : false

## Código
```
export const isPangram = (phrase: string): boolean => {
  const regex = /([a-z])(?!.*\1)/ig;
  const matches = phrase.match(regex);
  return matches !== null && matches.length === 26;
};
```

### Expresión regular
```
/([a-z])(?!.*\1)/ig;
```

**/** Delimita la regex

**i** Ignora capitalización al momento de la búsqueda, case-insensitive

**g** Modificador "global", lo que significa que la expresión regular buscará todas las coincidencias en toda la cadena y no se detendrá después de encontrar la primera coincidencia.

**([a-z])** Grupo de captura. Arroja un grupo de captura que coincida con los caracteres de la a-z

**(?!.*\1)** Negative lookahead. Esto es una construcción especial de expresiones regulares que verifica que lo que sigue a partir de este punto no contenga la misma letra capturada en el primer grupo. La sintaxis (?!) indica que no debe haber una coincidencia después del punto de verificación.

  **.*** Esto coincide con cualquier número de caracteres (excepto saltos de línea) que puedan aparecer entre la letra capturada y el punto de verificación.
  
  **\1** Retroreferencia al primer grupo de captura. Es decir, esto coincide con la misma letra que fue capturada por ([a-z]). Si la misma letra aparece después de la letra capturada, el lookahead falla y la expresión regular no hará una coincidencia.

