# Check if the sentence is a pangram

## Releer el problema

Dada una string llamada `sentence` verifica si este string contiene una vez todas las letras del alfabeto en inglés en minúsculas. La función debe retornar `true` si es así y `false` si no. 

## Ejemplos

```
sentence = "thequickbrownfoxjumpsoverthelazydog" 
checkIfPangran(sentence) => true

sentence = "iamtheproblem"
checkIfPangram(sentence) => false
```

## Aproximación del problema

- Solo letras del alfabeto de inglés (no incluyas la ñ)
- `return true` y `return false`
- `if` y `else` para ambos escenarios
- Esta es una string, no un array. 
- Iteración
- ¿método que itere y busque coincidencias?
- ¿Utilizar una expresión regular que contenga todo el alfabeto en inglés y en minúsculas?
- ¿Almacenar todo el alfabeto en una variable?
- Método includes: devuelve true si cumple la subcadena indicada entre paréntesis. Sintaxis: `string.includes(substring, position`*(opcional usar position)`)`

![image](https://user-images.githubusercontent.com/113146161/235035429-c2144be2-d301-4778-aec2-7ad25439f24d.png)

- Método every: devuelve true si el array (en nuestro caso, será cadena de texto) incluye la condición especificada. 

![image](https://user-images.githubusercontent.com/113146161/235036266-a976d3a6-0d21-4096-88a9-84bc5a40f982.png)

- Método split para separar cada caracter del alfabeto y que sea un array:

![image](https://user-images.githubusercontent.com/113146161/235038108-bda11f2a-fa71-410f-8f79-33e624c75186.png)

## Código

```
const sentence = "abcdefghijklmnopqrstuvwxyz";
const mustBeFalse = "thissentenceisnotapangram"

//El alfabeto se divide para así analizar por cada letra
const alphabet = "abcdefghijklmnopqrstuvwxyz".split("");

function checkIfPangram(sentence) {
    //Regresar true
    //Si para cada letra del alfabeto
    //La oración incluye cada letra
    return alphabet.every((letter) => sentence.includes(letter))
};

checkIfPangram(sentence);
```

## Test

![image](https://user-images.githubusercontent.com/113146161/235037537-b45d52ef-1576-44e1-9f06-c1c825c1a9a2.png)
