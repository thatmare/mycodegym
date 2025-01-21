# AdventJs: Reto 11:  Archivos encriptados ❌

[AdventJs: Reto 11:  Archivos encriptados ❌](https://adventjs.dev/challenges/2024/11)

The Grinch has hacked 🏴‍☠️ Santa Claus's workshop systems and has encoded the names of all the important files. Now the elves can't find the original files and they need your help to decipher the names.

Each file follows this format:
- It starts with a number (can contain any number of digits).
- Then has an underscore _.
- Continues with a file name and its extension.
- Ends with an extra extension at the end (which we don't need).
- Keep in mind that the file names may contain letters (a-z, A-Z), numbers (0-9), other underscores (_), and hyphens (-).

Your task is to implement a function that receives a string with the name of an encoded file and returns only the important part: the file name and its extension.

## Releer
El Grinch ha hackeado los sistemas del taller de Santa Claus y ha encriptado los nombres de todos los archivos importantes. Ahora, los elfos no pueden encontrar el archivo original y necesitan de tu ayuda para decifrar los nombres. 

Cada archivo contiene el siguiente formato:
- Empieza con un número (puede contener cualquier cantidad de dígitos).
- Tiene un guión bajo _.
- Continúa con el nombre del archivo y su extensión.
- Termina con una extensión extra al final (la cual no necesitamos).
- Considera que el nombre del archivo puede contener letras (a-z, A-Z), números (0-9), otros guiones bajos (_) y guiones (-).

Tu tarea es implementar una función que reciba una cadena de texto con el nombre del archivo encriptado y retorne solo la parte importante: el nombre del archivo y su extensión.

```typescript
function decodeFilename(filename: string): string {
    // Código aquí
    return ''
  }
```
## Ejemplos
```typescript
decodeFilename('2023122512345678_sleighDesign.png.grinchwa')
// ➞ "sleighDesign.png"

decodeFilename('42_chimney_dimensions.pdf.hack2023')
// ➞ "chimney_dimensions.pdf"

decodeFilename('987654321_elf-roster.csv.tempfile')
// ➞ "elf-roster.csv"
```
## Aproximación
### 1. Identificar la expresión regular para recuperar el nombre de archivo que nos interesa.
  - Descartar números.
  - Descartar el 1er guión bajo.
  - Después de las letras, recuperar:
      - El siguiente punto.
      - Los 3 caractéres siguientes.
### 2. Construir regex (expresión regular)
Con ayuda de [RegExr: Learn, Build & Test RegEx](https://regexr.com/) vamos a construir nuestra expresión regular. Vamos a desglosar paso por paso el significado de cada elemento de la.
- Vamos a colocar un ejemplo de input de la función.
- Arriba, estaremos jugando con la expresión regular; abajo, aparecerá la explicación de cada elemento de la.
<img width="950" alt="image" src="https://github.com/user-attachments/assets/b86964cf-bc20-43d2-af17-cc59438ff5be" />

#### 2.1 Iniciamos con las banderas en regex. Estas son caracteres que "envuelven" la y determinan el comportamiento. En este caso, agregaremos la `g` que viene de case **i**nsesitive para ignorar si es mayúscula o minúscula: `/[regex aquí]/i`.
a. Agregamos el guión bajo `_` para que busque ese caracter literalmente: `/_/i`.

b. Vamos a crear un grupo para buscar los caracteres, esto lo haremos con paréntesis: `/_()/i`.

c. Agregamos el punto `.` que va a incluir todos los caracteres, a excepción de los saltos de línea: `/_(.)/i`.

d. Agregamos `+` para incluir los caracteres siguientes: `/_(.+)/i`.

e. Agregamos `?` como cuantificaodr "lazy" (flojo), que buscará la menor cantidad de caracteres posible: `/_(.+?\.)/i`.

f. Agregamos `\.` como caracter de escape, es decir, el caracter en el cual se detiene la: `/_(.+?\.)/i`.

g. Después de nuestro caracter de espace, agregamos `[a-z]` para buscar la extensión: `/_(.+?\.[a-z]+)/i`.

h. Y `+` para incluir llos caracteres siguientes: `/_(.+?\.[a-z]+)/i`.

### 3. Agregamos el método `match()`.
- Este método devuelve todas las ocurrencias de la regex en un array. Como parámetro, agregaremos la regex que acabamos de construir.

### 4. Recuperar la coincidencia correcta
- El valor de retorno será un array con dos elementos, pues hay dos coincidencias del regex. Vamos a retornar el array en la posición `[1]`.
  
## Código
```javascript
function decodeFilename(filename) {
  let match = filename.match(/_(.+?\.[a-z]+)/i);
  return match[1];
}
```

Obtiene ⭐⭐⭐⭐⭐
## Enlaces y temas de interés
- [`match()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String/match): Devuelve todas las ocurrencias de una regex. 
- [Regex: Learn, Build & Test Regex](https://regexr.com/): Constructor de expresiones regulares con su expliación. 
