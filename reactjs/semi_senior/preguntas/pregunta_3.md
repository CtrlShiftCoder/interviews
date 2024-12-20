# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 3
**Crea un componente de React que maneje un formulario con dos campos: nombre y correo electrónico. Cuando el formulario se envíe, muestra los valores en un mensaje de confirmación sin recargar la página.**

**Respuesta:**

1. Crea un formulario controlado donde se gestionen los valores de los campos de entrada y se muestren los datos cuando el formulario se envíe.

**`Formulario.js`**:
```javascript
import React, { useState } from 'react';

function Formulario() {
  const [nombre, setNombre] = useState('');
  const [correo, setCorreo] = useState('');
  const [mensaje, setMensaje] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    setMensaje(`Gracias, ${nombre}! Hemos recibido tu correo: ${correo}`);
  };

  return (
    <div>
      <h2>Formulario de Contacto</h2>
      <form onSubmit={handleSubmit}>
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
          <label htmlFor="correo">Correo electrónico:</label>
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

      {mensaje && <p>{mensaje}</p>}
    </div>
  );
}

export default Formulario;
