# Botones alerta

- Crea una interfaz web que tenga 4 botones con los siguientes textos: Primero, Segundo, Tercero, Cuarto y Quinto.
- Crea una variable con el siguiente arreglo: ['Brasil', 'Chile', 'Colombia', 'México', 'Perú'].
- Cuando se hace clic en cada botón, debe alertar el país correspondiente a la posición correspondiente en el arreglo. Por ejemplo, hacer clic en Segundo debería alertar a 'Chile'.

```
const array = ['Brasil', 'Chile', 'Colombia', 'México', 'Perú'];

for(let i = 0; i < array.length; i++) {
  const btn = document.getElementById(`btn${i+1}`);
  
  btn.addEventListener('click', () => {
    alert(`${array[i]}`)
  })
}
```

## Optimización

```
<div id="botones">
  <button>Brasil</button>
  <button>Chile</button>
  <button>Colombia</button>
  <button>México</button>
  <button>Perú</button>
</div>

===============================================================

const array = ['Brasil', 'Chile', 'Colombia', 'México', 'Perú'];
const botonesContainer = document.getElementById('botones');

botonesContainer.addEventListener('click', (event) => {
  const boton = event.target;
  if (boton.tagName === 'BUTTON') {
    const index = Array.from(boton.parentNode.children).indexOf(boton);
    alert(`${array[index]}`);
  }
});
```
