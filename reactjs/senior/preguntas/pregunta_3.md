# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 3
**¿Cómo gestionarías el estado global de una aplicación React utilizando Context API?**

**Respuesta:**

La Context API de React se utiliza para compartir datos a través de la aplicación sin necesidad de pasar props manualmente en cada nivel de la jerarquía de componentes. Esto es útil cuando tienes información que necesita ser accesible en varios componentes, como la información de usuario, preferencias o configuraciones de la aplicación.

**Ejemplo:**

1. Crea el contexto utilizando `React.createContext()`.
2. Envuelve tu aplicación con un `Provider` para compartir el estado global.
3. Utiliza `useContext` en los componentes donde necesites acceder a los datos del contexto.

**`UserContext.js` (Creación del Contexto):**
```javascript
import React, { createContext, useState } from 'react';

// Crear el contexto
export const UserContext = createContext();

// Componente Provider para envolver la aplicación
export const UserProvider = ({ children }) => {
  const [user, setUser] = useState(null);

  const login = (username) => {
    setUser({ name: username });
  };

  const logout = () => {
    setUser(null);
  };

  return (
    <UserContext.Provider value={{ user, login, logout }}>
      {children}
    </UserContext.Provider>
  );
};
