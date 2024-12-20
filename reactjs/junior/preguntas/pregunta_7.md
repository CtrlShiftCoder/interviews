# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 7
**Crea un componente en React que muestre una lista de elementos, y permita al usuario eliminar un elemento al hacer clic en un botón "Eliminar".**

**Respuesta:**

1. Crea un componente que renderice una lista de elementos y permita al usuario eliminar uno al hacer clic en el botón correspondiente:

**`ListaConEliminar.js`**:
```javascript
import React, { useState } from 'react';

function ListaConEliminar() {
  const [elementos, setElementos] = useState(['Manzana', 'Banana', 'Cereza', 'Naranja']);

  // Función para eliminar un elemento
  const eliminarElemento = (index) => {
    const nuevosElementos = elementos.filter((_, i) => i !== index);
    setElementos(nuevosElementos);
  };

  return (
    <div>
      <ul>
        {elementos.map((elemento, index) => (
          <li key={index}>
            {elemento} 
            <button onClick={() => eliminarElemento(index)}>Eliminar</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default ListaConEliminar;
