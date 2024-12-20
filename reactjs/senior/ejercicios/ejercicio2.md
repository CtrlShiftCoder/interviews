# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 2
**Crea un componente que use el Hook `useEffect` para obtener datos de una API simulada cuando el componente se monte, y los muestre en una lista. Si hay un error en la solicitud, debe mostrar un mensaje de error.**

**Respuesta:**

1. Usaremos `useEffect` para realizar la solicitud a la API cuando el componente se monte.
2. Usaremos `useState` para manejar los datos obtenidos y los posibles errores.
3. Simularemos una API con `setTimeout` para demostrar la llamada asíncrona.

```javascript
import React, { useState, useEffect } from 'react';

// Simulación de una API que obtiene una lista de usuarios
const mockApi = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const success = true; // Cambiar a 'false' para simular un error
      if (success) {
        resolve([
          { id: 1, name: 'Juan Pérez' },
          { id: 2, name: 'Ana Gómez' },
          { id: 3, name: 'Carlos Martínez' },
        ]);
      } else {
        reject('Error al cargar los datos');
      }
    }, 1000);
  });
};

const UserList = () => {
  const [users, setUsers] = useState([]);
  const [error, setError] = useState('');

  useEffect(() => {
    const fetchData = async () => {
      try {
        const data = await mockApi();
        setUsers(data);
      } catch (err) {
        setError(err);
      }
    };

    fetchData();
  }, []); // El array vacío significa que solo se ejecutará una vez al montar el componente

  return (
    <div>
      <h1>Lista de Usuarios</h1>
      {error && <div style={{ color: 'red' }}>{error}</div>}
      <ul>
        {users.length > 0 ? (
          users.map((user) => (
            <li key={user.id}>{user.name}</li>
          ))
        ) : (
          <li>Cargando...</li>
        )}
      </ul>
    </div>
  );
};

export default UserList;
