# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 7
**Crea un componente de formulario que permita a un usuario ingresar su nombre y correo electrónico. Al enviar el formulario, muestra los datos ingresados en la pantalla.**

**Respuesta:**

1. Crea un formulario con campos para el nombre y correo electrónico, y muestra los datos después de enviarlo.

**`Formulario.js`**:
```javascript
import React, { useState } from 'react';

function Formulario() {
  const [nombre, setNombre] = useState('');
  const [correo, setCorreo] = useState('');
  const [enviado, setEnviado] = useState(false);

  const manejarEnvio = (e) => {
    e.preventDefault();
    setEnviado(true);
  };

  return (
    <div>
      <h2>Formulario</h2>
      <form onSubmit={manejarEnvio}>
        <div>
          <label htmlFor="nombre">Nombre:</label>
          <input
            type="text"
            id="nombre"
            value={nombre}
            onChange={(e) => setNombre(e.target.value)}
            required
          />
        </div>
        <div>
          <label htmlFor="correo">Correo Electrónico:</label>
          <input
            type="email"
            id="correo"
            value={correo}
            onChange={(e) => setCorreo(e.target.value)}
            required
          />
        </div>
        <button type="submit">Enviar</button>
      </form>

      {enviado && (
        <div>
          <h3>Datos enviados:</h3>
          <p>Nombre: {nombre}</p>
          <p>Correo: {correo}</p>
        </div>
      )}
    </div>
  );
}

export default Formulario;
