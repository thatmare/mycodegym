# Sum of digits

## Releer

Dado n, tome la suma de los dígitos de n. Si ese valor tiene más de un dígito, continúe reduciendo de esta manera hasta que se produzca un número de un solo dígito. La entrada será un número entero no negativo.
- Tengo que sumar
- Tengo que dividir el número n hasta que **todos los elementos de n sean un solo dígito**. 
- Entra número, sale número

## Ejemplos

```
[942] => 9+4+2 => 15 > 1 + 5 => 6
[123] => 1+2+3 => 6
```

## Aproximación

- Pasar numero a string para poder dividirlo
- Dividir el input tal vez con split. 
- Esto me da un array de strings. 
- Necesito que cada elemento del array sea un número. 
- Para después poder sumarlo. 
- Y esto debe de repetirse hasta que sea un solo número.
- La fx deberá detenerse cuando llegue a un número.

## Código

```
function digitalRoot(n){
    while(n > 9) {
    let arrStr = String(n).split('');
    let arrNum = arrStr.map(x => Number(x));
    let x = arrNum.reduce((a, b) => a + b, 0);  
        n = x;
    }
    return n;
}
```

## Test

## Optimizar
