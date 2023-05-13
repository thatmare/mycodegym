# convertScoreToGrade

[convertScoreToGrade](https://curriculum.laboratoria.la/es/topics/javascript/arrays/practice/convert-score-to-grade)

## Releer

Escribe una función llamada convertScoreToGrade.
Dada una puntuación, convertScoreToGrade devuelve una cadena que representa el grado de letra correspondiente a la puntuación dada.
Si la puntuación dada es mayor que 100 o menor que 0, debe devolver 'PUNTUACION INVALIDA'.
- Voy a recibir siempre valores numéricos
- El output es un string

## Ejemplos
(100 - 90) -> 'A'
(89 - 80) ->' B '
(79 - 70) -> 'C'
(69 - 60) -> 'D'
(59 - 0) -> 'F
```
(93) => 'A'
(76) => 'C'
(88) => 'B'
(55) => 'F'
```

## Aproximación
- Establecer rangos numéricos
- Condicionados: contemplar todos los escenarios de output if/else if
- Agregar puntuación inválida
- Optimizar más adelante ternario 

## Código

```
const convertScoreToGrade = (score) => {
    if(score >= 90 && score <= 100) {
        return 'A'
    } else if(score >= 80 && score <= 89) {
      return 'B'
    } else if (score >= 70 && score <= 79) {
        return 'C'
    } else if(score >= 60 && score <= 69) {
        return 'D'
    } else if(score >= 0 && score <= 59) {
        return 'F'
    } else {
        return 'PUNTUACION INVALIDA'
    }
};
```
## Test

![image](https://github.com/thatmare/mycodegym/assets/113146161/316d0503-cc1a-4034-8870-559711e8b16e)

## Optimizar

```
const convertScoreToGrade = (score) => {
  return (score >= 90 && score <= 100) ? 'A' :
         (score >= 80 && score <= 89) ? 'B' :
         (score >= 70 && score <= 79) ? 'C' :
         (score >= 60 && score <= 69) ? 'D' :
         (score >= 0 && score <= 59) ? 'F' : 'PUNTUACION INVALIDA';
};

=========================================================================================

const convertScoreToGrade = (score) => {
  const gradeRanges = {
    'A': [90, 100],
    'B': [80, 89],
    'C': [70, 79],
    'D': [60, 69],
    'F': [0, 59]
  };
  
  for (let grade in gradeRanges) {
    if (score >= gradeRanges[grade][0] && score <= gradeRanges[grade][1]) {
      return grade;
    }
  }
  
  return 'PUNTUACION INVALIDA';
};

```
