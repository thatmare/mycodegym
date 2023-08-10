# Two to one

## Releer

Toma dos cadenas de texto, s1 y s2, que incluyen letras de la a - z. Retorna una nueva cadena de texto ordenada, l más larga posible, conteniendo distintas letras, tomando solo una de la cadena s1 y de la s2.

## Ejemplificar

```
a = 'xxoooomkmjkk'
b = 'areyouready'
longest(a, b) => 'adejkmoruxy'

a = "xyaabbbccccdefww"
b = "xxxxyyyyabklmopq"
longest(a, b) -> "abcdefklmopqwxy"

a = "abcdefghijklmnopqrstuvwxyz"
longest(a, a) -> "abcdefghijklmnopqrstuvwxyz"
```

## Aproximación

- Separar la cadena de texto con split para crear un array.
- Hacer sort en el array.
- Unir ambos arrays de haber dos.
- Insertar los elementos en un set para que no se repitan.
- Unirlos en una cadena de texto.

## Código

```
export const longest = (s1:string, s2:string): string => {
  const arr = (s1 + s2).split('').sort();
  const set1 = new Set(arr);
  const myIterator = set1.values();
  
  let text = "";
  for (const entry of myIterator) {
    text += entry;
  }

  return text;
}
```

## Explicación

```
export const longest = (s1:string, s2:string): string => {
// concatenamos las cadenas de texto, las convertimos en un array y se ordenan alfabéticamente
  const arr = (s1 + s2).split('').sort();
// con el array anterior creamos un objeto Set: los sets no permiten que los valores se repitan
  const set1 = new Set(arr);
// creamos un objeto iterador con el método de 'values()', específicamente es método de Set
// un objeto iterador contiene dos propiedades: value y done, y un método llamado next()
// como su nombre lo indica, es posible iterar sobre dicho objeto
  const myIterator = set1.values();

// usamos un bucle for...of para iterar sobre myIterator. Inicializamos una cadena vacía para agregar cada elemento del objeto
  let text = "";
  for (const entry of myIterator) {
    text += entry;
  }

  return text;
}
```

## Optimizar

```
export const longest = (s1: string, s2: string): string =>
  [...new Set([...s1, ...s2])].sort().join("");
```
