# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 1
**Crea un componente de lista de tareas (to-do list) que permita a los usuarios agregar, eliminar y marcar como completadas las tareas. Implementa la funcionalidad de persistencia usando `localStorage` para que las tareas se mantengan después de recargar la página.**

**Respuesta:**

1. Implementa un componente de lista de tareas con funcionalidades de agregar, eliminar y marcar como completadas, con persistencia usando `localStorage`.

**`TodoList.js`**:
```javascript
import React, { useState, useEffect } from 'react';

function TodoList() {
  // Estado para las tareas
  const [task, setTask] = useState('');
  const [tasks, setTasks] = useState([]);

  // Cargar tareas desde localStorage al montar el componente
  useEffect(() => {
    const savedTasks = JSON.parse(localStorage.getItem('tasks'));
    if (savedTasks) {
      setTasks(savedTasks);
    }
  }, []);

  // Guardar tareas en localStorage cada vez que cambian
  useEffect(() => {
    localStorage.setItem('tasks', JSON.stringify(tasks));
  }, [tasks]);

  // Función para agregar una tarea
  const addTask = () => {
    if (task.trim() !== '') {
      setTasks([...tasks, { id: Date.now(), text: task, completed: false }]);
      setTask('');
    }
  };

  // Función para eliminar una tarea
  const deleteTask = (id) => {
    setTasks(tasks.filter((task) => task.id !== id));
  };

  // Función para marcar una tarea como completada
  const toggleTaskCompletion = (id) => {
    setTasks(
      tasks.map((task) =>
        task.id === id ? { ...task, completed: !task.completed } : task
      )
    );
  };

  return (
    <div>
      <h2>Lista de Tareas</h2>
      <input
        type="text"
        value={task}
        onChange={(e) => setTask(e.target.value)}
        placeholder="Escribe una tarea..."
      />
      <button onClick={addTask}>Agregar</button>

      <ul>
        {tasks.map((task) => (
          <li key={task.id} style={{ textDecoration: task.completed ? 'line-through' : 'none' }}>
            <span onClick={() => toggleTaskCompletion(task.id)}>{task.text}</span>
            <button onClick={() => deleteTask(task.id)}>Eliminar</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default TodoList;
