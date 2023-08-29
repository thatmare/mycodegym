# mapBully

[The Winter Hub: mapBully](https://the-winter.github.io/codingjs/exercise.html?name=mapBully&title=Map-1)

Modifica y retorna el objeto: si la clave "a" tiene valor, cambia la o agrega una clave "b" para que tenga ese valor, y modifica el valor de la clave "a" para que su valor sea "". 

## Releer

- El valor de la clave "a" será asignado al valor de la clave "b".
- Puede o no haber la clave "a": hay que corroborar si existe o no.
- Puede o no haber la clave "b": de no haber, agregarla.
- Si no hay clave a o b, el objeto se retorna igual.

## Ejemplos

```
mapBully({'a': 'candy', 'b': 'dirt'}) → {'a': '', 'b': 'candy'}
mapBully({'a': 'candy'}) → {'a': '', 'b': 'candy'}
mapBully({'a': 'candy', 'b': 'carrot', 'c': 'meh'}) → {'a': '', 'b': 'candy', 'c': 'meh'}
```

## Aproximación

- Se pude acceder al valor de una propiedad de un objeto con la destructuración: `someMap['a']`.
- Corroborar si existe el par clave-valor "a".
- De existir, corroborar si existe la clave "b": si existe, modificar; si no existe, agregar.
- Si existen ambos, reasignar (`=`) los valores.

## Código

```
function mapBully(someMap){
  if (!someMap['a']) {
    console.log(someMap)
  } else if (someMap['a'] && !someMap['b']) {
    someMap.b = someMap['a'];
    someMap['a'] = '';
    console.log(someMap) ;
  } else {
    someMap['b'] = someMap['a'];
    someMap['a'] = '';
    console.log(someMap);
  } 
}
```
