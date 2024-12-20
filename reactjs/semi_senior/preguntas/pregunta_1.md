# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 1
**Crea un componente en React que gestione un formulario con campos de nombre y correo electrónico. Al enviar el formulario, los datos deben mostrarse en una lista debajo del formulario.**

**Respuesta:**

1. Crea un componente que contenga un formulario con campos de nombre y correo electrónico, y que al enviar los datos, los muestre en una lista:

**`Formulario.js`**:
```javascript
import React, { useState } from 'react';

function Formulario() {
  const [nombre, setNombre] = useState('');
  const [email, setEmail] = useState('');
  const [usuarios, setUsuarios] = useState([]);

  // Maneja el cambio en el campo 'nombre'
  const handleNombreChange = (event) => {
    setNombre(event.target.value);
  };

  // Maneja el cambio en el campo 'email'
  const handleEmailChange = (event) => {
    setEmail(event.target.value);
  };

  // Maneja el envío del formulario
  const handleSubmit = (event) => {
    event.preventDefault();
    // Agrega el nuevo usuario a la lista
    setUsuarios([...usuarios, { nombre, email }]);
    // Limpia los campos del formulario
    setNombre('');
    setEmail('');
  };

  return (
    <div>
      <h2>Formulario de Usuario</h2>
      <form onSubmit={handleSubmit}>
        <div>
          <label>Nombre:</label>
          <input 
            type="text" 
            value={nombre} 
            onChange={handleNombreChange} 
            required 
          />
        </div>
        <div>
          <label>Email:</label>
          <input 
            type="email" 
            value={email} 
            onChange={handleEmailChange} 
            required 
          />
        </div>
        <button type="submit">Agregar Usuario</button>
      </form>

      <h3>Usuarios Agregados</h3>
      <ul>
        {usuarios.map((usuario, index) => (
          <li key={index}>
            {usuario.nombre} - {usuario.email}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default Formulario;
