# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 3
**Crea un componente en React que contenga un formulario con un campo de texto. Cuando el usuario ingresa texto y hace clic en el botón, el texto debe mostrarse debajo del formulario.**

**Respuesta:**

1. Crea el componente usando React y maneja el estado con el hook `useState` para capturar el valor ingresado en el campo de texto:

**`FormularioTexto.js`**:
```javascript
import React, { useState } from 'react';

function FormularioTexto() {
  // Estado para manejar el texto ingresado
  const [texto, setTexto] = useState('');
  const [mostrarTexto, setMostrarTexto] = useState('');

  // Función para manejar el envío del formulario
  const manejarEnvio = (e) => {
    e.preventDefault();
    setMostrarTexto(texto);
  };

  return (
    <div>
      <form onSubmit={manejarEnvio}>
        <input
          type="text"
          value={texto}
          onChange={(e) => setTexto(e.target.value)}
          placeholder="Escribe algo..."
        />
        <button type="submit">Enviar</button>
      </form>
      {mostrarTexto && <p>Texto ingresado: {mostrarTexto}</p>}
    </div>
  );
}

export default FormularioTexto;
