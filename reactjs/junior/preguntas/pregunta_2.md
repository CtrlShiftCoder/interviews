# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 2
**Crea un componente en React que contenga un botón. Cuando se haga clic en el botón, debe cambiar el texto que se muestra en la pantalla.**

**Respuesta:**

1. Crea el componente funcional usando React, y maneja el estado con el hook `useState`:

**`CambioTexto.js`**:
```javascript
import React, { useState } from 'react';

function CambioTexto() {
  // Usamos useState para definir el estado del texto
  const [texto, setTexto] = useState('Texto inicial');

  // Función para cambiar el texto
  const cambiarTexto = () => {
    setTexto('Texto cambiado!');
  };

  return (
    <div>
      <p>{texto}</p>
      <button onClick={cambiarTexto}>Cambiar Texto</button>
    </div>
  );
}

export default CambioTexto;
