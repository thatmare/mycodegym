# Red Ticket

[Red Ticket](https://the-winter.github.io/codingjs/exercise.html?name=redTicket&title=Logic-1)

## Releer el problema

Tienes un billete de lotería rojo que muestra los enteros a, b y c, cada uno de los cuales es 0, 1 o 2. Si todos tienen el valor 2, el resultado es 10. Si son todos iguales, el resultado es 5. Si b y c son diferentes de a, el resultado es 1. Si no, el resultado es 0.

## Ejemplos 

```
redTicket(2, 2, 2) -> 10
redTicket(1, 1, 1) -> 5
redTicket(0, 1, 1) -> 1
redTicket(0, 1, 3) -> 1
redTicket(1, 3, 0) -> 0
```

## Aproximación 

- Usar operadores para mostrar igualdad == y diferencia != 
- Usar `if` y `else if` para todos los escenarios

## Código

```
function redTicket(a, b, c){
  if (a == 2 && b == 2 && c == 2) {
  return 10
  } else if (a == b && b == c && a == c) {
  return 5
  } else if (a != c && a != b) {
  return 1
  } else {
  return 0
  }
}
```

## Test

![image](https://user-images.githubusercontent.com/113146161/232936862-48df6ae0-d58d-4aaa-aa2b-c2350746087c.png)
