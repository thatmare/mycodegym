# Merged Sorted Array

You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array nums1. To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. nums2 has a length of n.


Example 1:

Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
Output: [1,2,2,3,5,6]
Explanation: The arrays we are merging are [1,2,3] and [2,5,6].
The result of the merge is [1,2,2,3,5,6] with the underlined elements coming from nums1.

## Releer

- Se dan dos arrays de números, nums1 y nums2
- Estos números están ordenados de manera ascendente
- Se dan dos números enteros
- Hasta ahora, llevamos 4 parámetros: 2 arrays de números y 2 números enteros
- El param "m" representa la longitud de nums1 y el param "n" la longitud de nums2
- El objetivo es concatenar nums1 y nums2 en un solo array de manera ascendente
- La condición es que el array resultante no debe ser nuevo, sino el array nums1 alterado
- El array rsultante tendrá la longitud m + n

## Ejemplos

````
nums1 = [1,5,7,8]
m = 2
nums2 = [4,7,9]
n = 2

=> nums1 = [1,4,5,7]

````

## Aproximación
- Recuperar el último elemento de cada array.

## Código

````
function merge(nums1: number[], m: number, nums2: number[], n: number): void {
    let i = m - 1; // último elemento del array nums1
    let j = n - 1; // último elemento del array nums2
    let k = m + n - 1; // último elemento del array resultante (nums1)

    while (i >= 0 && j >= 0) { // mientras que el último elemento de nums1 sea igual o mayor a 0 y el último elemento de nums2 sea igual o mayor a cero, se va a ejecutar...
        if (nums1[i] > nums2[j]) { // si el último de nums1 es mayor al último de nums2
            nums1[k] = nums1[i]; // agrega el último de nums1 al arreglo resultante
            i--; // y decrementa el valor de la última posición de nums1
        } else { // en otro caso
            nums1[k] = nums2[j]; // agrega el último de nums2 al arreglo resultante
            j--; // y decrementa el valor de la última posición de nums2
        }
        k--; // decrementa el valor de la última posición del arreglo resultante
    }

    while (j >= 0) {
        nums1[k] = nums2[j];
        j--;
        k--;
    }
}
````
