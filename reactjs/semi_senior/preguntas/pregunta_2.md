# Pruebas Técnicas para React con Respuestas y Ejemplos

## Semi Senior

### Ejercicio 2
**Crea un componente en React que haga una llamada a una API externa (puedes usar una API pública como JSONPlaceholder) y muestre una lista de elementos (por ejemplo, posts).**

**Respuesta:**

1. Crea un componente que haga una llamada a la API cuando se monte, obtenga los datos y los muestre en una lista.

**`Posts.js`**:
```javascript
import React, { useState, useEffect } from 'react';

function Posts() {
  const [posts, setPosts] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState('');

  useEffect(() => {
    // Hacemos la llamada a la API cuando el componente se monta
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json())
      .then((data) => {
        setPosts(data); // Guardamos los posts en el estado
        setLoading(false); // Cambiamos el estado de carga
      })
      .catch((error) => {
        setError('Error al cargar los datos');
        setLoading(false);
      });
  }, []); // El array vacío asegura que la llamada solo se haga una vez

  if (loading) {
    return <div>Cargando...</div>;
  }

  if (error) {
    return <div>{error}</div>;
  }

  return (
    <div>
      <h2>Lista de Posts</h2>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>
            <h3>{post.title}</h3>
            <p>{post.body}</p>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default Posts;
