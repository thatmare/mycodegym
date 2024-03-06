# Two Sum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 ## Releer
 - Vamos a recibir dos parámetros: un array de números enteros y un número entero (target).
 - El output son dos índices (en un array) que indiquen las posiciones de:
 - Dos elementos dentro del primer array que, sumados, retornen el target

 ## Ejemplos

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]

## Aproximación

- Crear la variable de `complement`, esta almacena la resta del número `target` menos el número actual de la iteración.
- Iteramos sobre el array
- Almacenamos el número actual y su posición en un objeto.
- Si los pares clave-valor coinciden con el número `complement`, se retorna su posición en el array.

##Código

````
function twoSum(nums: number[], target: number): number[] {
    const numMap = {};

    for (let i = 0; i < nums.length; i++) {
        const complement = target - nums[i];

        if (numMap.hasOwnProperty(complement)) {
            return [numMap[complement], i];
        }

        numMap[nums[i]] = i;
    }

    return [];
}

````
