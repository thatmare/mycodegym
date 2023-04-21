# Create Phone Number

[Codewars: Create Phone Number](https://www.codewars.com/kata/525f50e3b73515a6db000b83/train/javascript)

## Releer el problema

La función recibirá un arreglo de 10 números del 0 al 9. El resultado de esa función deben de ser esos diez números en formato de número telefónico, con paréntesis, espacio y guión. Nota que la entrada es dato numérico y la salida es string. 

## Ejemplos

```
[1, 2, 3, 4, 5, 6, 7, 8, 9 0] -> "(123) 456-7890"
```

## Aproximación

- Utilizaremos el método `slice` para separar los grupos de números a partir de un index. 
- Utilizaremos el método `join` para unir estos grupos, ya sea por paréntesis, espacio o guión. 
- Vamos a concatenar.

## Código

```
function createPhoneNumber(numbers){

//regresar el arreglo de números dividos desde la posición 0 a la 3 unidos por ""... y así concatenamos de la misma manera
return "(" + numbers.slice(0,3).join("") + ")"
+ " " + numbers.slice(3,6).join("") + "-" + numbers.slice(6,10).join("");
}
```
