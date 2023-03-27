# Codewars: Jaden Casing Strings

[Jaden Casing Strings](https://www.codewars.com/kata/5390bac347d09b7da40006f6/train/javascript)

## Releer el problema
Para cualquier string, debemos de capitalizar/transformar a mayúscula la primera letra de cada palabra. Este reto está inspirado en el Twitter de Jaden Smith, quien suele tuitear frases "filosóficas" con este tipo de escritura. Hay que prestar atención en las letras después de las apóstrofes ('), esas no se capitalizan.

## Ejemplos

```
Not Jaden-Cased: "How can mirrors be real if our eyes aren't real"
Jaden-Cased:     "How Can Mirrors Be Real If Our Eyes Aren't Real"

"Cualquier frase va aquí" -> "Cualquier Frase Va Aquí"
"Hace mucho calor hoy" -> "Hace Mucho Calor Hoy"
"The apostrophes won't be capitalized" -> "The Apostrophes Won't Be Capitalized"
```

## Aproximación

- Hay que recibir el dato tipo string.
- `toUpperCase` es un método que sirve para pasar de minúsculas a mayúsculas.
- ¿Se podría crear una variable que recupere la primera letra de cada palabra y aplicar la función a esa variable?
- `split` Vamos a dividir la cadena usando como separador el carácter "espacio" (' '). En este caso el carácter espacio funciona como el separador o divisor. Esto nos ayuda a separar las palabras.

![image](https://user-images.githubusercontent.com/113146161/227643872-5cbe5bee-49d6-44d8-b3e9-3f4ee1bec3af.png)

- `map` El método map() crea un nuevo array con los resultados de la llamada a la función indicada aplicados a cada uno de sus elementos.
- `slice` El método slice nos devuelve una parte del string. Pueden ser dos parámetros, que marcan el inicio y el fin del corte, o un parámetro que indique a partir de dónde se hace el corte.

![image](https://user-images.githubusercontent.com/113146161/227643836-8dc187ac-335b-4419-970c-e3ca023c0ee2.png)

- `join` El método join() une todos los elementos de una matriz (o un objeto similar a una matriz) en una cadena y devuelve esta cadena.

![image](https://user-images.githubusercontent.com/113146161/227644512-e9d49a1b-885d-4fcc-aaed-ae3527fdda82.png)

Es decir:
1. Vamos a separar cada palabra.
2. Para cada palabra, tomaremos la primera letra.
3. Capitalizaremos cada primera letra.
4. La uniremos con el resto de la palabra.
5. Uniremos todas las palabras.

## Code

```
String.prototype.toJadenCase = function() {

  //return this permite que la función se aplique al mismo objeto que está recibiendo. 
  return this
  
  //separa la cadena por sus espacios: nos deja las palabras solamente
  .split(" ")
  
  //map recorre el objeto y ejecuta lo siguiente para cada uno de los elementos del objeto
  //en este caso, se declara la variable word, que va a ser cada palabra en su posición 0 (la primera letra), que será transformada a mayúscula, y esta se va a concatenar con el resto de la palabra que ha sido dividida a partir de la primera letra
  .map(word => word[0].toUpperCase() + word.slice(1))
  
  //lo anterior, será unido con el espacio
  .join(" ");
}
```

## Test

![image](https://user-images.githubusercontent.com/113146161/228070561-cc025e8e-79d2-42ea-9c74-ff38857c5027.png)

## Optimizar
- Agregar una validación para que solo reciba string.
- Considerar otros caracteres además del espacio.

## Enlaces
- [Split de JavaScript](https://www.freecodecamp.org/espanol/news/el-split-de-javascript-como-dividir-una-cadena-de-caracteres-en-un-arreglo-con-js/)
- [Map](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [Join](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
