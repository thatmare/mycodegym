# Highest And Lowest

## Releer el problema

In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.

## Ejemplos

```
highAndLow("1 2 3 4 5");  // return "5 1"
highAndLow("1 2 -3 4 5"); // return "5 -3"
highAndLow("1 9 3 4 -5"); // return "9 -5"

```

## Aproximación

// input string
// output string
// string to number to compare?
// Hay que transformarlos en números para poder hacer operaciones matemáticas
// Ordenar de mayor a menor
// Extraer primera y última posición

## Código

```
function highAndLow(numbers){
  let nums = numbers.split(' ');
  let orderedNums = nums.map(n => Number(n)).sort((a, b) => b - a);
  return `${orderedNums[0] + ' ' + orderedNums[orderedNums.length-1]}`
}

```

## Optimizar

```
function highAndLow(numbers){
  numbers = numbers.split(' ');
  return `${Math.max(...numbers)} ${Math.min(...numbers)}`;
}

```
