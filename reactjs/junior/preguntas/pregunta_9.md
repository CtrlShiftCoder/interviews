# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 9
**Crea un componente en React que muestre una lista de tareas. Cada tarea debe tener un botón para marcarla como completada. Al hacer clic, la tarea debe cambiar de estilo para indicar que ha sido completada.**

**Respuesta:**

1. Crea un componente que maneje una lista de tareas y permita marcar cada una como completada al hacer clic en un botón:

**`Tareas.js`**:
```javascript
import React, { useState } from 'react';

function Tareas() {
  const [tareas, setTareas] = useState([
    { id: 1, texto: 'Comprar pan', completada: false },
    { id: 2, texto: 'Hacer ejercicio', completada: false },
    { id: 3, texto: 'Estudiar React', completada: false },
  ]);

  // Función para marcar una tarea como completada
  const marcarCompletada = (id) => {
    const nuevasTareas = tareas.map((tarea) =>
      tarea.id === id ? { ...tarea, completada: !tarea.completada } : tarea
    );
    setTareas(nuevasTareas);
  };

  return (
    <div>
      <ul>
        {tareas.map((tarea) => (
          <li 
            key={tarea.id} 
            style={{ textDecoration: tarea.completada ? 'line-through' : 'none' }}
          >
            {tarea.texto} 
            <button onClick={() => marcarCompletada(tarea.id)}>
              {tarea.completada ? 'Desmarcar' : 'Marcar como completada'}
            </button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default Tareas;
