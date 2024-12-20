# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 1  
**¿Qué es un componente en Angular?**  

**Respuesta:**  
Un componente en Angular es una de las unidades básicas de construcción de una aplicación. Representa una parte de la interfaz de usuario (UI) y está compuesto por:  
- Un archivo HTML para la vista.  
- Un archivo TypeScript para la lógica.  
- Un archivo CSS o SCSS para los estilos.

**Ejemplo:**  
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-mi-componente',
  template: `
    <h1>¡Hola, Angular!</h1>
    <p>Este es mi primer componente.</p>
  `,
  styles: [`
    h1 {
      color: blue;
    }
  `]
})
export class MiComponente {
  mensaje: string = 'Bienvenido a Angular';
}
