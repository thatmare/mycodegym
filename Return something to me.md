# Return something to me

[Return something to me](https://edabit.com/challenge/MvZK536X7fyrWH8Qc)

## Releer el problema

Elaborar una función que regrese el string `"something"` + espacio `" "` + un argumento dado `a`. Es decir, se devolverá una frase, una oración, un enunciado. ❗*Hay que hacer la función para cualquier tipo de input.*

## Ejemplos

```
giveMeSomething("is better than nothing") ➞ "something is better than nothing"

giveMeSomething("Bob Jane") ➞ "something Bob Jane"

giveMeSomething("something") ➞ "something something"

giveMeSomething("to me") -> "something to me"

giveMeSomething("to eat") -> "something to eat"
```

## Aproximación
- Hay que declarar el string de `"something "` para concatenarlo.
- La principal acción de la función es regresar, así que hay que agregar `return`.
- Para concatenar, hay que agregar el operado + el argumento a: `+ a`.

## Code

Primer intento

![image](https://user-images.githubusercontent.com/113146161/227375305-982eb845-6e05-42c8-93ca-8868058a7073.png)

La variable `a` queda de manera local dentro de la función y por eso no resulta.

## Test

![image](https://user-images.githubusercontent.com/113146161/227375453-11021fca-6ec5-4540-b465-11fe58e83eb7.png)
