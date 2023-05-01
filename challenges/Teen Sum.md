# Teen Sum

[The Winter: Teen Sum](https://the-winter.github.io/codingjs/exercise.html?name=teenSum&title=Logic-1)

## Releer el problema

Dados dos enteros, a y b, regresa su suma: a excepción de cuando a o b se encuentren entre 13 y 19, esos son los valores "adolescentes". Cuando así sea, regresa solamente el 19. 
- Es decir, no importa si solo un entero está entre 13 o 19, el resultado deberá ser 19. 

## Ejemplos

```
teenSum(1, 2) -> 3
teenSum(12, 11) -> 23
teenSum(13, 1) -> 19
teenSum(5, 18) -> 19
```

## Aproximación

- Son dos escenarios: en un escenario se suman a y b, y en el otro no se suma: en este segundo escenario, debemos identificar el número para saber si se sumará  no. Entonces, si son dos escenarios, necesitamos dos condiciones: `if` y `else`. 
- Sabemos que en un escenario la condición será a + b. 
- En el otro escenario, debemos de establecer el rango: si a es igual o mayor a 13 y es igual o menor a 19. 
- Usaremos operadores de comparación: >=, =>, &&, ||. 

## Código

```
function teenSum(a, b){
  //Si a es mayor o igual a trece Y es menor o igual a 19 O si b es igual o menor a 13 Y b es menor o igual a 19...
  if (a >= 13 && a <= 19 || b >= 13 && b <= 19) {
  //regresa 19
  return 19
  
  //en cualquier otro caso
  } else {
  //regresa la suma de a + b
  return a + b
  }
}
```

## Test

![image](https://user-images.githubusercontent.com/113146161/233658221-19491abe-c24c-4544-846f-6f06b0dc390b.png)
