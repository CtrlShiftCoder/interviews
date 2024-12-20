# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 6
**Crea un componente que simule una lista de usuarios. Cada usuario debe tener un botón para mostrar u ocultar sus detalles.**

**Respuesta:**

1. Crea un componente que gestione una lista de usuarios con un botón para mostrar y ocultar detalles adicionales sobre cada usuario.

**`ListaDeUsuarios.js`**:
```javascript
import React, { useState } from 'react';

function ListaDeUsuarios() {
  const [usuarios] = useState([
    { id: 1, nombre: 'Juan', detalles: 'Detalles de Juan: Edad 30, Ubicación: Madrid' },
    { id: 2, nombre: 'Ana', detalles: 'Detalles de Ana: Edad 25, Ubicación: Barcelona' },
    { id: 3, nombre: 'Luis', detalles: 'Detalles de Luis: Edad 35, Ubicación: Valencia' },
  ]);

  const [detallesVisible, setDetallesVisible] = useState({});

  const toggleDetalles = (id) => {
    setDetallesVisible((prevState) => ({
      ...prevState,
      [id]: !prevState[id],
    }));
  };

  return (
    <div>
      <h2>Lista de Usuarios</h2>
      <ul>
        {usuarios.map(usuario => (
          <li key={usuario.id}>
            <p>{usuario.nombre}</p>
            <button onClick={() => toggleDetalles(usuario.id)}>
              {detallesVisible[usuario.id] ? 'Ocultar detalles' : 'Mostrar detalles'}
            </button>
            {detallesVisible[usuario.id] && <p>{usuario.detalles}</p>}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default ListaDeUsuarios;
