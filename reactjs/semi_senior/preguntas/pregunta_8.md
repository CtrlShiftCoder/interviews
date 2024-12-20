# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 8
**Crea un componente que reciba una lista de elementos como props y los muestre en una lista ordenada. Además, cada elemento debe tener un botón para eliminarlo de la lista.**

**Respuesta:**

1. Crea un componente que reciba una lista de elementos y permita eliminar un elemento de la lista al hacer clic en el botón de eliminar.

**`Lista.js`**:
```javascript
import React, { useState } from 'react';

function Lista({ elementos }) {
  const [lista, setLista] = useState(elementos);

  const eliminarElemento = (index) => {
    const nuevaLista = lista.filter((_, i) => i !== index);
    setLista(nuevaLista);
  };

  return (
    <div>
      <h2>Lista de Elementos</h2>
      <ul>
        {lista.map((elemento, index) => (
          <li key={index}>
            {elemento} 
            <button onClick={() => eliminarElemento(index)}>Eliminar</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default Lista;
