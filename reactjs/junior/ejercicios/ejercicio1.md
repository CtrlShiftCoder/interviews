# Pruebas Técnicas para React con Respuestas y Ejemplos

## Junior

### Ejercicio 1
**Crea un componente de React que reciba una lista de nombres como prop y los muestre en una lista ordenada.**

**Respuesta:**

1. Primero, crea el componente usando React:

```javascript
import React from 'react';

const ListaNombres = ({ nombres }) => {
  return (
    <div>
      <h2>Lista de Nombres:</h2>
      <ul>
        {nombres.map((nombre, index) => (
          <li key={index}>{nombre}</li>
        ))}
      </ul>
    </div>
  );
};

const App = () => {
  const listaDeNombres = ['Juan', 'Pedro', 'Ana', 'Laura'];

  return (
    <div>
      <ListaNombres nombres={listaDeNombres} />
    </div>
  );
};

export default App;
