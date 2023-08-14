# Make Array Consecutive 2

[Make Array Consecutive 2](https://app.codesignal.com/arcade/intro/level-2/bq2XnSr5kbHqpHGJC)

Ratiorg got statues of different sizes as a present from CodeMaster for his birthday, each statue having an non-negative integer size. Since he likes to make things perfect, he wants to arrange them from smallest to largest so that each statue will be bigger than the previous one exactly by 1. He may need some additional statues to be able to accomplish that. Help him figure out the minimum number of additional statues needed.

Example

For statues = [6, 2, 3, 8], the output should be
solution(statues) = 3.

Ratiorg needs statues of sizes 4, 5 and 7.

## Releer

- Vamos a recibir un array de números.
- Vamos a ordenarlos de menor a mayor.
- Deseamos que la diferencia entre cada número consecutivo sea de 1: como no es así, hipotéticamente, insertaríamos números que cumplan con esto.
- Lo que debemos de retornar es la cantidad de números que habría que insertar en el array.

## Ejemplos

```
[1, 4, 6, 7] => 3, porque nos hacen falta el 2, 3 y 5: 5 nums
[3, 4, 5] => 0, porque todos los nums tienen una distancia de 1 entre ellos mismos
[6, 7, 9, 11, 15] => 5, porque hacen falta 8, 10, 12, 13 y 14: 5 nums
```

## Aproximación

- Lo primero será ordenar los números con sort.
- Iterar sobre el array y comparar el número previo con el siguiente.
- Inicializar una variable en 0, llamada total
- Comparar el numero prev con el sig: si la diferencia entre ambos es de 1, no se suma nada al total
- Si la diferencia entre ambos es igual a 0, no se suma nada al total
- Cualquier otra diferencia, se suma la diferenca - 1

## Código

```
function solution(statues: number[]): number {
	const sorted = statues.sort((a, b) => a - b);
    let total = 0;
  
  for (let i = 0; i < sorted.length-1; i++) {
  	let difference = sorted[i+1] - sorted[i];
    if(difference <= 1) {
    	total += 0;
    } else {
    	total += (difference-1);
    }
  }
    return total;
}
```

## Optimizar
```
function solution(statues: number[]): number {
	const sorted = statues.sort((a, b) => a - b);
    let total = 0;
  
  for (let i = 0; i < sorted.length-1; i++) {
  	let difference = sorted[i+1] - sorted[i];
    
    difference <= 1 ? total += 0 : total += difference-1;
  }
    return total;
}

=================================================
function solution(statues: number[]): number {
	const sorted = statues.sort((a, b) => a - b);
    let total = 0;
  
for (let i = 0; i < sorted.length - 1; i++) {
        const difference = sorted[i + 1] - sorted[i];

        if (difference > 1) {
            total += difference - 1;
        }
    }
    return total;
}
```
