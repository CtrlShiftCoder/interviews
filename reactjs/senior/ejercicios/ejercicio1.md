# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 1
**Crea un componente que maneje la autenticación de usuario utilizando un formulario de inicio de sesión. El componente debe contener validación de campos, un estado para manejar los errores, y mostrar un mensaje de éxito al iniciar sesión correctamente. El formulario debe enviar una solicitud a una API simulada.**

**Respuesta:**

1. Usaremos `useState` para manejar los estados del formulario, los errores y el estado de la autenticación.
2. Implementamos una función que simula la llamada a una API para realizar el login.
3. Mostramos un mensaje de error si la autenticación falla o un mensaje de éxito si se realiza correctamente.

```javascript
import React, { useState } from 'react';

// Simulación de una API de autenticación
const mockAuthApi = (username, password) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (username === 'admin' && password === 'password123') {
        resolve({ message: 'Inicio de sesión exitoso' });
      } else {
        reject({ message: 'Credenciales incorrectas' });
      }
    }, 1000);
  });
};

const LoginForm = () => {
  const [username, setUsername] = useState('');
  const [password, setPassword] = useState('');
  const [error, setError] = useState('');
  const [success, setSuccess] = useState('');

  const handleSubmit = async (e) => {
    e.preventDefault();
    setError('');
    setSuccess('');

    if (!username || !password) {
      setError('Por favor, ingresa tu nombre de usuario y contraseña');
      return;
    }

    try {
      const response = await mockAuthApi(username, password);
      setSuccess(response.message);
    } catch (error) {
      setError(error.message);
    }
  };

  return (
    <div>
      <h1>Inicio de sesión</h1>
      <form onSubmit={handleSubmit}>
        <div>
          <label htmlFor="username">Nombre de usuario:</label>
          <input
            type="text"
            id="username"
            value={username}
            onChange={(e) => setUsername(e.target.value)}
          />
        </div>
        <div>
          <label htmlFor="password">Contraseña:</label>
          <input
            type="password"
            id="password"
            value={password}
            onChange={(e) => setPassword(e.target.value)}
          />
        </div>
        <button type="submit">Iniciar sesión</button>
      </form>

      {error && <div style={{ color: 'red' }}>{error}</div>}
      {success && <div style={{ color: 'green' }}>{success}</div>}
    </div>
  );
};

export default LoginForm;
