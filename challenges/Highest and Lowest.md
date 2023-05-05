# Highest and Lowest

## Releer
- Dado un string, devuelve el mayor número y el menor número. 
- Cada número siempre estará separado por un espacio.
- El primer número devuelto debe ser el mayor. 
- Los números serán devueltos con un espacio entre ellos.
- El resultado también será un string.
- Siempre habrá un número en el string.

## Ejemplos

```
highAndLow("1 2 3 4 5") => "5 1"
highAndLow("3 5 7 8 2 6 2") => "8 2"
highAndLow("-5 9 1 -6 8") => "9 -6"
```

## Aproximación

- Separar cada número con split(" ").
- Recorrer cada elemento con map.
- Transformar cada elemento en un número
- Ordenar los elementos con sort.
- Retornar la primera y última posición [0] y [n.length-1]

## Código

```
function highAndLow(numbers){
  let nums = numbers.split(" ").map(n => Number(n)).sort((a,b) => a < b ? 1 : -1);
  return String(nums[0] + " " + nums[nums.length-1]); 
}


```

## Test

![image](https://user-images.githubusercontent.com/113146161/236356009-e36bee4b-1952-481e-a21e-9d04577f1b00.png)


## Optimizar

```
function highAndLow(numbers){
  let nums = numbers.split(" ").map(n => Number(n)).sort((a,b) => b - a);
  return nums[0] + " " + nums[nums.length-1]; 
}

function highAndLow(numbers){
  numbers = numbers.split(' ');
  return `${Math.max(...numbers)} ${Math.min(...numbers)}`;
}
```

![image](https://user-images.githubusercontent.com/113146161/236356431-a0f167ae-847e-4251-81a0-6794a9af8b80.png)

- Math.max y Math.min retornan el número mayor y menor, respectivamente, de cero o más números dados como parámetros de entrada. 
- Devuelve NaN si no es un número o no puede ser convertido a un número.
- La segunda solución funciona con el spread operator (...) ya que las funciones Math.max() y Math.min() no están diseñadas para tomar un array como argumento. En lugar de eso, toman una lista de argumentos separados. El operador ... se utiliza para expandir los elementos del array como una lista de argumentos.
- La sintaxis ${} es un tipo de interpolación de cadena en JavaScript que permite incluir expresiones dentro de una cadena de texto
