# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 5
**Crea un componente en React que reciba un array de números como prop y muestre la suma de esos números.**

**Respuesta:**

1. Crea el componente usando React que reciba un array de números como `prop` y calcule la suma de esos números:

**`SumaNumeros.js`**:
```javascript
import React from 'react';

function SumaNumeros({ numeros }) {
  // Calcular la suma de los números en el array
  const suma = numeros.reduce((acc, num) => acc + num, 0);

  return (
    <div>
      <p>La suma de los números es: {suma}</p>
    </div>
  );
}

export default SumaNumeros;
