# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 4
**Crea un componente que simule una lista de tareas. Cada tarea debe tener una opción para marcarla como completada (con un checkbox) y otra para eliminarla de la lista.**

**Respuesta:**

1. Crea un componente que gestione una lista de tareas con la capacidad de marcar como completada y eliminar tareas.

**`ListaDeTareas.js`**:
```javascript
import React, { useState } from 'react';

function ListaDeTareas() {
  const [tareas, setTareas] = useState([
    { id: 1, texto: 'Aprender React', completada: false },
    { id: 2, texto: 'Hacer ejercicio', completada: false },
    { id: 3, texto: 'Leer un libro', completada: false },
  ]);

  const toggleCompletada = (id) => {
    setTareas(tareas.map(tarea => 
      tarea.id === id ? { ...tarea, completada: !tarea.completada } : tarea
    ));
  };

  const eliminarTarea = (id) => {
    setTareas(tareas.filter(tarea => tarea.id !== id));
  };

  return (
    <div>
      <h2>Lista de Tareas</h2>
      <ul>
        {tareas.map(tarea => (
          <li key={tarea.id} style={{ textDecoration: tarea.completada ? 'line-through' : 'none' }}>
            <input 
              type="checkbox" 
              checked={tarea.completada} 
              onChange={() => toggleCompletada(tarea.id)} 
            />
            {tarea.texto}
            <button onClick={() => eliminarTarea(tarea.id)}>Eliminar</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default ListaDeTareas;
