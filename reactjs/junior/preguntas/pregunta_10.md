# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 10
**Crea un componente en React que tenga un contador que se pueda incrementar y decrementar con dos botones. El valor del contador debe mostrarse en pantalla.**

**Respuesta:**

1. Crea un componente que tenga dos botones para incrementar y decrementar el valor de un contador:

**`Contador.js`**:
```javascript
import React, { useState } from 'react';

function Contador() {
  const [contador, setContador] = useState(0);

  // Función para incrementar el contador
  const incrementar = () => {
    setContador(contador + 1);
  };

  // Función para decrementar el contador
  const decrementar = () => {
    setContador(contador - 1);
  };

  return (
    <div>
      <h2>Contador: {contador}</h2>
      <button onClick={incrementar}>Incrementar</button>
      <button onClick={decrementar}>Decrementar</button>
    </div>
  );
}

export default Contador;
