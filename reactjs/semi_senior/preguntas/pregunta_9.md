# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 9
**Crea un componente que reciba un valor numérico como prop, y muestre ese valor como un contador que se incrementa automáticamente cada segundo. El contador debe poder detenerse cuando el usuario haga clic en un botón "Detener".**

**Respuesta:**

1. Crea un componente que reciba un valor numérico como prop y aumente ese valor automáticamente cada segundo hasta que el usuario haga clic en un botón "Detener".

**`Contador.js`**:
```javascript
import React, { useState, useEffect } from 'react';

function Contador({ valorInicial }) {
  const [valor, setValor] = useState(valorInicial);
  const [activo, setActivo] = useState(true);

  useEffect(() => {
    if (activo) {
      const intervalo = setInterval(() => {
        setValor((prevValor) => prevValor + 1);
      }, 1000);

      // Limpiar el intervalo cuando el componente se desmonta o cuando se detiene el contador
      return () => clearInterval(intervalo);
    }
  }, [activo]);

  const detenerContador = () => {
    setActivo(false);
  };

  return (
    <div>
      <h2>Contador: {valor}</h2>
      <button onClick={detenerContador}>Detener</button>
    </div>
  );
}

export default Contador;
