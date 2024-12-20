# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 10
**Crea un formulario con dos campos: uno para ingresar un nombre y otro para ingresar un correo electrónico. El formulario debe validar que ambos campos no estén vacíos y mostrar un mensaje de error si el usuario intenta enviarlo con campos vacíos.**

**Respuesta:**

1. Crea un formulario con dos campos de entrada y un botón de envío. Validar que los campos no estén vacíos antes de permitir el envío del formulario.

**`Formulario.js`**:
```javascript
import React, { useState } from 'react';

function Formulario() {
  const [nombre, setNombre] = useState('');
  const [email, setEmail] = useState('');
  const [error, setError] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!nombre || !email) {
      setError('Ambos campos son obligatorios');
    } else {
      setError('');
      alert('Formulario enviado con éxito');
    }
  };

  return (
    <div>
      <h2>Formulario de Inscripción</h2>
      <form onSubmit={handleSubmit}>
        <div>
          <label htmlFor="nombre">Nombre:</label>
          <input
            type="text"
            id="nombre"
            value={nombre}
            onChange={(e) => setNombre(e.target.value)}
          />
        </div>
        <div>
          <label htmlFor="email">Correo Electrónico:</label>
          <input
            type="email"
            id="email"
            value={email}
            onChange={(e) => setEmail(e.target.value)}
          />
        </div>
        {error && <p style={{ color: 'red' }}>{error}</p>}
        <button type="submit">Enviar</button>
      </form>
    </div>
  );
}

export default Formulario;
