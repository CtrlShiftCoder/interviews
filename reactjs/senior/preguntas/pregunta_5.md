# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 5
**¿Qué es el "Context API" en React y cómo lo usarías para compartir estado entre componentes?**

**Respuesta:**

El **Context API** en React es una herramienta que permite compartir valores y estado entre componentes sin tener que pasar props manualmente a través de cada nivel del árbol de componentes. Esto es útil para valores globales como el tema de la UI, la autenticación del usuario, y configuraciones globales.

**Ejemplo:**

1. **Crear un Contexto**: Usamos `React.createContext()` para crear un contexto. Esto nos proporciona un `Provider` para envolver la parte de la aplicación que necesita acceder al contexto y un `Consumer` o `useContext` para acceder a los valores dentro de los componentes.

2. **Usar el Provider**: El `Provider` permite definir el valor del contexto que se quiere compartir.

3. **Acceder al contexto**: Dentro de los componentes que necesitan acceder al estado global, usamos el hook `useContext` o el `Consumer`.

**Ejemplo de uso del Context API:**

1. **Crear el contexto y el proveedor:**

```javascript
import React, { createContext, useState } from 'react';

// Crear el contexto
const AuthContext = createContext();

// Componente proveedor
export const AuthProvider = ({ children }) => {
  const [isAuthenticated, setIsAuthenticated] = useState(false);

  const login = () => setIsAuthenticated(true);
  const logout = () => setIsAuthenticated(false);

  return (
    <AuthContext.Provider value={{ isAuthenticated, login, logout }}>
      {children}
    </AuthContext.Provider>
  );
};
