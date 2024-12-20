# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 4
**¿Cómo manejarías los efectos secundarios en React usando `useEffect`?**

**Respuesta:**

`useEffect` es un hook de React que permite realizar efectos secundarios en componentes funcionales, tales como llamadas a APIs, suscripciones, o manipulaciones del DOM. Se ejecuta después de que el componente se haya renderizado, lo que hace posible realizar operaciones que dependen de cambios en el estado o las props.

**Ejemplo:**

1. **Efectos secundarios en la carga inicial del componente (solo una vez al montar):**
   Si se quiere ejecutar el efecto solo una vez cuando el componente se monta (similar a `componentDidMount`), se pasa un array vacío `[]` como segundo argumento de `useEffect`.

2. **Efectos secundarios con dependencia (cuando cambian ciertas variables):**
   Si se quiere que el efecto se ejecute cada vez que una variable específica cambie, se pasa esa variable dentro del array de dependencias.

**Ejemplo de uso de `useEffect`:**

```javascript
import React, { useState, useEffect } from 'react';

function FetchData() {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);

  // Usando useEffect para llamar a la API
  useEffect(() => {
    // Función asíncrona para obtener datos
    const fetchData = async () => {
      try {
        const response = await fetch('https://api.example.com/data');
        const result = await response.json();
        setData(result); // Actualizar el estado con los datos
      } catch (error) {
        console.error('Error fetching data:', error);
      } finally {
        setLoading(false); // Actualizar el estado de carga
      }
    };

    fetchData(); // Llamada a la API

    // El efecto solo se ejecuta una vez al montar el componente
  }, []); // El array vacío significa que el efecto se ejecuta solo al montar

  return (
    <div>
      {loading ? (
        <p>Cargando...</p>
      ) : (
        <ul>
          {data.map((item, index) => (
            <li key={index}>{item.name}</li>
          ))}
        </ul>
      )}
    </div>
  );
}

export default FetchData;
