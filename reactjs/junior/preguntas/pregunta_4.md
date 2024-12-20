# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 4
**Crea un componente en React que muestre un contador. El contador debe incrementar su valor cada vez que el usuario haga clic en un botón.**

**Respuesta:**

1. Crea el componente usando React y el hook `useState` para manejar el valor del contador:

**`Contador.js`**:
```javascript
import React, { useState } from 'react';

function Contador() {
  // Estado para manejar el valor del contador
  const [contador, setContador] = useState(0);

  // Función para incrementar el contador
  const incrementar = () => {
    setContador(contador + 1);
  };

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={incrementar}>Incrementar</button>
    </div>
  );
}

export default Contador;
