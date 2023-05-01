# Codewars: Sentence Smash

[Codewars: Sentence Smash](https://www.codewars.com/kata/53dc23c68a0c93699800041d/train/javascript)

## Releer el problema

Crear una función que regrese las palabras de un array a manera de oración, unidas por espacios entre ellas. 

## Ejemplos

```
["hello", "have", "a", "nice", "day"] => "hello have a nice day"
["vamos", "por", "algo", "para", "comer"] => "vamos por algo para comer"
```

## Aproximación

- Método `.join` para unir strings.
- `return` para arrojar/regresar el nuevo array. 

## Code

```
function newSmash(words){
    //El parámetro recibido va a ser unido por un espacio " "
    return words.join(" ")
}
```

## Test

![image](https://user-images.githubusercontent.com/113146161/228266881-ef58c3df-432b-4164-a283-90ec88f5ae9b.png)
