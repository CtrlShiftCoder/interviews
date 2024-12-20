# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 2
**Crea un componente que muestre una lista de tareas y permita agregar nuevas tareas a la lista. Cada tarea debe tener un título y un estado (completa o pendiente). Además, debe haber un botón para marcar una tarea como completada.**

**Respuesta:**

1. Crea el componente usando `useState` para gestionar las tareas y su estado (completa o pendiente).

```javascript
import React, { useState } from 'react';

const ListaTareas = () => {
  const [tareas, setTareas] = useState([
    { id: 1, titulo: 'Hacer compras', completada: false },
    { id: 2, titulo: 'Lavar los platos', completada: false },
  ]);
  
  const [titulo, setTitulo] = useState('');

  const agregarTarea = () => {
    if (titulo.trim() === '') return;
    const nuevaTarea = { id: Date.now(), titulo, completada: false };
    setTareas([...tareas, nuevaTarea]);
    setTitulo('');
  };

  const marcarCompletada = (id) => {
    setTareas(tareas.map(tarea =>
      tarea.id === id ? { ...tarea, completada: !tarea.completada } : tarea
    ));
  };

  return (
    <div>
      <h1>Lista de Tareas</h1>
      <input
        type="text"
        value={titulo}
        onChange={(e) => setTitulo(e.target.value)}
        placeholder="Nueva tarea"
      />
      <button onClick={agregarTarea}>Agregar</button>

      <ul>
        {tareas.map((tarea) => (
          <li key={tarea.id} style={{ textDecoration: tarea.completada ? 'line-through' : 'none' }}>
            {tarea.titulo}
            <button onClick={() => marcarCompletada(tarea.id)}>
              {tarea.completada ? 'Desmarcar' : 'Completar'}
            </button>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default ListaTareas;
