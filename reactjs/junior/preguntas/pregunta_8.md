# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 8
**Crea un componente en React que permita a un usuario ingresar su nombre en un campo de texto y luego mostrar un saludo personalizado cuando haga clic en un botón.**

**Respuesta:**

1. Crea un componente que tenga un campo de texto para que el usuario ingrese su nombre, y un botón para mostrar un saludo personalizado:

**`SaludoPersonalizado.js`**:
```javascript
import React, { useState } from 'react';

function SaludoPersonalizado() {
  const [nombre, setNombre] = useState('');
  const [saludo, setSaludo] = useState('');

  // Función para manejar el cambio en el campo de texto
  const manejarCambio = (event) => {
    setNombre(event.target.value);
  };

  // Función para generar el saludo
  const generarSaludo = () => {
    setSaludo(`¡Hola, ${nombre}!`);
  };

  return (
    <div>
      <input 
        type="text" 
        placeholder="Ingresa tu nombre" 
        value={nombre} 
        onChange={manejarCambio} 
      />
      <button onClick={generarSaludo}>Saludar</button>
      {saludo && <h2>{saludo}</h2>}
    </div>
  );
}

export default SaludoPersonalizado;
