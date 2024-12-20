# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 2  
**¿Qué es el `ngFor` en Angular y para qué se utiliza?**  

**Respuesta:**  
`ngFor` es una directiva estructural en Angular que se utiliza para iterar sobre una colección (como un array) y renderizar un elemento HTML para cada ítem de la colección.

**Ejemplo:**  
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-lista-usuarios',
  template: `
    <h1>Lista de usuarios</h1>
    <ul>
      <li *ngFor="let usuario of usuarios">
        {{ usuario }}
      </li>
    </ul>
  `,
})
export class ListaUsuariosComponent {
  usuarios: string[] = ['Juan', 'María', 'Carlos', 'Ana'];
}
