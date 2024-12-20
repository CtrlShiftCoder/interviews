# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 7
**¿Cómo manejarías el estado global en una aplicación React sin usar `Redux`?**

**Respuesta:**

En React, puedes manejar el estado global sin usar Redux utilizando el **Context API**. El Context API permite compartir valores entre componentes sin necesidad de pasar props manualmente a través de toda la jerarquía de componentes. Esto es útil para manejar datos que se necesitan en muchos lugares de la aplicación, como la información del usuario, configuraciones globales, o el tema de la interfaz.

**Sintaxis de `useContext`:**
1. Primero, creas un contexto con `React.createContext()`.
2. Luego, envuelves tu componente de nivel superior en un proveedor de contexto (`Context.Provider`).
3. Finalmente, puedes acceder al valor del contexto en cualquier componente hijo usando `useContext(Context)`.

**Ejemplo:**

1. **Crear un contexto de autenticación:**

```javascript
import React, { createContext, useContext, useState } from 'react';

// Crear el contexto
const AuthContext = createContext();

// Componente proveedor para envolver la aplicación
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

// Componente para acceder al contexto
const Navbar = () => {
  const { isAuthenticated, login, logout } = useContext(AuthContext);

  return (
    <nav>
      <p>{isAuthenticated ? 'Bienvenido, Usuario' : 'No autenticado'}</p>
      <button onClick={isAuthenticated ? logout : login}>
        {isAuthenticated ? 'Cerrar sesión' : 'Iniciar sesión'}
      </button>
    </nav>
  );
};

export default Navbar;
