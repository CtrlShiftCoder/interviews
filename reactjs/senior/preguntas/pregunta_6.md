# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 6
**¿Cómo manejarías los efectos secundarios en React utilizando el hook `useEffect`?**

**Respuesta:**

El hook `useEffect` en React se utiliza para manejar efectos secundarios en componentes funcionales, como la manipulación del DOM, la llamada a APIs, o la suscripción a eventos. `useEffect` se ejecuta después de que el componente se haya renderizado, lo que lo hace ideal para tareas como obtener datos, configurar temporizadores, o realizar limpieza de recursos.

**Sintaxis de `useEffect`:**
```javascript
useEffect(() => {
  // Código que se ejecuta después de cada renderizado

  return () => {
    // Limpieza de efectos, se ejecuta antes de que el componente se desmonte o antes de la siguiente ejecución del efecto
  };
}, [dependencias]);
