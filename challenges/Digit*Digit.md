# Digit* Digit

[Codewars: Digit*Digit](https://www.codewars.com/kata/546e2562b03326a88e000020/train/javascript)

## Releer

- Crear una función que devuelva el cuadrado de cada número.
- Que el cuadrado de cada número sea concatenado.
- La función acepta un entero y regresa un entero. 
- Estamos recibiendo un *valor numérico*, no un array de numéros ni un string.
- Igualmente se debe de devolver un valor numérico.

## Ejemplos

```
squareDigits(3212) => 9414;
squareDigits(9732) => 814992;
squareDigits(0) => 0;
squareDigits(159) => 12581;
```

## Aproximación
- Transformar el valor numérico a un string.
- El string será dividido con split para que así sea un número en un array.
- Entonces, se va a iterar en cada número.
- A cada número se le aplicará el cuadrado: Math.pow(base, exponente)
- Cada numero será unido con el método join.
- Y este será transformado en un valor numérico con el método Number o parseInt.

## Código
```
function squareDigits(num){
    let n = num.toString().split("");

    return Number(n.map(x => Math.pow(x, 2)).join(""));
};
```

## Test

![image](https://user-images.githubusercontent.com/113146161/236076474-cb0855c8-b285-4e03-86ae-6dd5a3b97ce5.png)

![image](https://user-images.githubusercontent.com/113146161/236076526-4ec5fba5-7b08-4bbf-99eb-6a1bbe9deded.png)

![image](https://user-images.githubusercontent.com/113146161/236076595-f642362e-9f45-4acf-8680-63575b9b6921.png)

![image](https://user-images.githubusercontent.com/113146161/236076619-0a8a177a-0891-4e1b-8737-1c10101dbeaa.png)


## Optimizar

```
const squareDigits = (num) => {
  return (num = parseInt(
    num
      .toString()
      .split('')
      .map((digit) => digit * digit)
      .join('')
  ))
}
```
