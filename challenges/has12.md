# has12

[The Winter Hub: has12](https://the-winter.github.io/codingjs/exercise.html?name=has12&title=Array-2)

## Releer

- Vas a recibir un array de números enteros.
- Devolver true si dentro del array se encuentra el número 1 Y el número 2. No es excluyente, deben estar AMBOS. 
- El 2 debe de estar después del 1 para devolver true. 

## Ejemplos

## Aproximación

## Código

```
function has12(nums){
    let has1 = false;
    for (let index = 0; index < nums.length; index++) {
        if(nums[index] === 1) {
            has1 = true;
        } else if(has1 && nums[index] == 2) {
            return true;
        }
    }
  return false;
}
```

## Test

## Optimizar
