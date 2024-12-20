# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 7  
**¿Qué son las directivas en Angular y cuántos tipos existen?**  

**Respuesta:**  
Las directivas en Angular son instrucciones en el DOM que permiten modificar su apariencia o comportamiento. Se usan para aplicar lógica o manipular elementos HTML dinámicamente.

Existen tres tipos de directivas:  
1. **Directivas de atributo:** Cambian la apariencia o el comportamiento de un elemento existente.  
   - Ejemplo: `ngClass`, `ngStyle`.  
2. **Directivas estructurales:** Alteran el DOM agregando o eliminando elementos.  
   - Ejemplo: `*ngIf`, `*ngFor`.  
3. **Directivas personalizadas:** Son creadas por los desarrolladores para agregar funcionalidades específicas.

**Ejemplo:**  
1. **Uso de una directiva estructural (`*ngIf`):**  
```typescript
@Component({
  selector: 'app-bienvenida',
  template: `
    <div *ngIf="mostrarMensaje">
      ¡Bienvenido a Angular!
    </div>
  `,
})
export class BienvenidaComponent {
  mostrarMensaje: boolean = true;
}
