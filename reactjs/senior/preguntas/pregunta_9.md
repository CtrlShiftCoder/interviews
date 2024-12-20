# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 9
**¿Qué es el contexto (Context API) en React y cómo se usa?**

**Respuesta:**

El **Context API** es una herramienta de React que permite compartir datos a través de la aplicación sin tener que pasar propiedades manualmente a cada nivel de la jerarquía de componentes. Es útil cuando se necesitan compartir datos globales como el usuario autenticado, temas de la interfaz de usuario, configuraciones, etc.

Contexto en React ayuda a evitar el **prop drilling**, es decir, el paso de props de un componente a otro de forma excesiva, especialmente cuando los componentes están profundamente anidados.

**Cómo usar Context API en React:**

1. **Crear un contexto.**
2. **Proveer el contexto en un componente superior.**
3. **Consumir el contexto en los componentes hijos.**

**Ejemplo de uso de Context API:**

```javascript
import React, { createContext, useState, useContext } from 'react';

// 1. Crear un contexto
const UserContext = createContext();

const UserProvider = ({ children }) => {
  // 2. Definir el estado que se quiere compartir
  const [user, setUser] = useState(null);

  const login = (name) => {
    setUser(name);
  };

  return (
    // 3. Proveer el contexto a los componentes hijos
    <UserContext.Provider value={{ user, login }}>
      {children}
    </UserContext.Provider>
  );
};

const UserProfile = () => {
  // Consumir el contexto en un componente hijo
  const { user, login } = useContext(UserContext);

  return (
    <div>
      {user ? (
        <h1>Bienvenido, {user}!</h1>
      ) : (
        <button onClick={() => login('Juan')}>Iniciar sesión</button>
      )}
    </div>
  );
};

const App = () => {
  return (
    <UserProvider>
      <UserProfile />
    </UserProvider>
  );
};

export default App;
