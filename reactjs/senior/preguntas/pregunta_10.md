# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 10
**¿Cómo optimizar el rendimiento de una aplicación React utilizando React.memo y useMemo?**

**Respuesta:**

**React.memo** y **useMemo** son dos herramientas que ayudan a optimizar el rendimiento en aplicaciones React, especialmente cuando los componentes son costosos de renderizar o recalcular.

- **React.memo**: Es un componente de orden superior que previene la renderización innecesaria de un componente. Solo vuelve a renderizar el componente si las props han cambiado.

- **useMemo**: Es un hook que memoriza el valor calculado de una expresión o función y lo reusa hasta que alguna de las dependencias cambie. Es útil para evitar cálculos costosos en cada render.

### Uso de `React.memo`:

**React.memo** envuelve un componente para prevenir su renderizado innecesario cuando las props no han cambiado.

**Ejemplo:**

```javascript
import React from 'react';

const ComponentePesado = React.memo(({ contador }) => {
  console.log("ComponentePesado renderizado");
  return <div>Contador: {contador}</div>;
});

const App = () => {
  const [contador, setContador] = React.useState(0);
  const [nombre, setNombre] = React.useState('Juan');

  return (
    <div>
      <ComponentePesado contador={contador} />
      <button onClick={() => setContador(contador + 1)}>Incrementar contador</button>
      <button onClick={() => setNombre(nombre === 'Juan' ? 'Pedro' : 'Juan')}>Cambiar nombre</button>
    </div>
  );
};

export default App;
