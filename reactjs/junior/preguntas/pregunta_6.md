# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 6
**Crea un componente en React que muestre un mensaje personalizado que cambia dependiendo de la hora del día (mañana, tarde, noche).**

**Respuesta:**

1. Crea un componente que use la función `Date` para obtener la hora actual y mostrar un mensaje basado en el horario:

**`SaludoPorHora.js`**:
```javascript
import React from 'react';

function SaludoPorHora() {
  // Obtener la hora actual
  const horaActual = new Date().getHours();
  let saludo = '';

  // Determinar el saludo según la hora
  if (horaActual >= 6 && horaActual < 12) {
    saludo = '¡Buenos días!';
  } else if (horaActual >= 12 && horaActual < 18) {
    saludo = '¡Buenas tardes!';
  } else {
    saludo = '¡Buenas noches!';
  }

  return (
    <div>
      <h1>{saludo}</h1>
    </div>
  );
}

export default SaludoPorHora;
