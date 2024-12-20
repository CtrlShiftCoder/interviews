# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 1
**Crea un componente de React que reciba una lista de objetos con `nombre` y `edad`, y muestre los elementos en una tabla. Además, debe permitir ordenar la tabla por nombre o edad al hacer clic en los encabezados de las columnas.**

**Respuesta:**

1. Primero, crea el componente utilizando `useState` y `useEffect` para manejar el estado y el orden de los elementos:

```javascript
import React, { useState } from 'react';

const TablaPersonas = ({ personas }) => {
  const [ordenadoPor, setOrdenadoPor] = useState('nombre');
  const [personasOrdenadas, setPersonasOrdenadas] = useState(personas);

  const ordenarPor = (campo) => {
    const nuevasPersonas = [...personas].sort((a, b) => {
      if (a[campo] < b[campo]) return -1;
      if (a[campo] > b[campo]) return 1;
      return 0;
    });
    setPersonasOrdenadas(nuevasPersonas);
    setOrdenadoPor(campo);
  };

  return (
    <table>
      <thead>
        <tr>
          <th onClick={() => ordenarPor('nombre')}>Nombre</th>
          <th onClick={() => ordenarPor('edad')}>Edad</th>
        </tr>
      </thead>
      <tbody>
        {personasOrdenadas.map((persona, index) => (
          <tr key={index}>
            <td>{persona.nombre}</td>
            <td>{persona.edad}</td>
          </tr>
        ))}
      </tbody>
    </table>
  );
};

const App = () => {
  const listaDePersonas = [
    { nombre: 'Juan', edad: 25 },
    { nombre: 'Ana', edad: 30 },
    { nombre: 'Pedro', edad: 22 },
    { nombre: 'Laura', edad: 28 },
  ];

  return (
    <div>
      <h1>Tabla de Personas</h1>
      <TablaPersonas personas={listaDePersonas} />
    </div>
  );
};

export default App;
