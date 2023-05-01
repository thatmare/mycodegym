# Reverse Words

[Codwars: Reverse Words](https://www.codewars.com/kata/5259b20d6021e9e14c0010d4/train/javascript)

## Releer el problema

Crear una función que acepte solamente strings. Cada palabra debe de estar en reversa. Conservar los espacios. Conservar el orden de la palabra. 

## Ejemplos

```
"This is an example!" ==> "sihT si na !elpmaxe"
"double  spaces"      ==> "elbuod  secaps"
"Marissa is coding" => "assiraM si gnidoc"
```

## Aproximación 

- Crear una condicional que solo acepte strings. 
- Separar cada palabra y para cada palabra aplicar la reversa. 
- Unir con `.join()`.

![image](https://user-images.githubusercontent.com/113146161/235463120-23bf81b4-622c-4720-be08-36ed01f08995.png)


## Código

```
function reverseWords(str) {
  //Si el tipo de argumento es string, entonces...
  if(typeof str === 'string') {
    //regresar cada uno dividido: recuerda que regresará un array
    return str.split("")
    //revertir el orden del array(en este caso, de las letras): recuerda que aquí las primeras letras pasarán al final
    .reverse()
    //unir(recuerda que se están uniendo con espacios)
    .join("")
    //dividir a partir de los espacios(es decir, cada palabra)
    .split(" ")
    //revertir el orden de las palabras: ahora, las últimas quedarán al principio y viceversa
    .reverse()
    //unir con espacios
    .join(" ");
  } else {
    return null;
  }
}
```
