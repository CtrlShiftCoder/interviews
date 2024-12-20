# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 1
**Crea un componente funcional en React que reciba un nombre como propiedad (`props`) y lo muestre en una etiqueta `<h1>` dentro del componente.**

**Respuesta:**

1. Crea el componente funcional usando React:

**`Saludo.js`**:
```javascript
import React from 'react';

function Saludo(props) {
  return (
    <h1>¡Hola, {props.nombre}!</h1>
  );
}

export default Saludo;
