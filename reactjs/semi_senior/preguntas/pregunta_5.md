# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 5
**Crea un componente que simule un contador con botones para incrementar y decrementar el valor. El valor debe mostrarse en la pantalla y no debe bajar de cero.**

**Respuesta:**

1. Crea un componente con dos botones: uno para incrementar el valor y otro para decrementar. Asegúrate de que el valor no pueda ser menor que cero.

**`Contador.js`**:
```javascript
import React, { useState } from 'react';

function Contador() {
  const [contador, setContador] = useState(0);

  const incrementar = () => {
    setContador(contador + 1);
  };

  const decrementar = () => {
    if (contador > 0) {
      setContador(contador - 1);
    }
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
