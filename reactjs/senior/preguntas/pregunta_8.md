# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 8
**¿Qué son los hooks en React y cómo se utilizan?**

**Respuesta:**

Los **hooks** son funciones especiales de React que permiten a los componentes funcionales manejar estado, efectos secundarios y otras características que antes solo estaban disponibles en componentes de clase. Los hooks fueron introducidos en React 16.8 y proporcionan una forma más concisa y modular de manejar la lógica del componente.

Los dos hooks más comunes son:
1. **`useState`**: Para manejar el estado dentro de un componente funcional.
2. **`useEffect`**: Para manejar efectos secundarios, como la actualización del DOM o la llamada a APIs.

**Ejemplo de uso de `useState` y `useEffect`:**

```javascript
import React, { useState, useEffect } from 'react';

const FetchData = () => {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  // Usamos useEffect para llamar a la API cuando el componente se monta
  useEffect(() => {
    fetch('https://api.example.com/data')
      .then((response) => response.json())
      .then((data) => {
        setData(data);
        setLoading(false);
      });
  }, []); // El array vacío significa que el efecto solo se ejecutará una vez al montar el componente

  if (loading) {
    return <p>Loading...</p>;
  }

  return (
    <div>
      <h1>Data fetched from API:</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
};

export default FetchData;
