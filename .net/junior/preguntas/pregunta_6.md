# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 6  
**¿Qué es un módulo en Angular y por qué es importante?**  

**Respuesta:**  
Un módulo en Angular es un contenedor que agrupa componentes, directivas, servicios y otros módulos relacionados. Los módulos ayudan a organizar la aplicación en bloques funcionales, facilitando la gestión del código y la reutilización de funcionalidades.

**Ejemplo:**  

1. **Creación de un módulo:**  
```typescript
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { UsuariosComponent } from './usuarios/usuarios.component';

@NgModule({
  declarations: [UsuariosComponent], // Componentes del módulo
  imports: [CommonModule], // Módulos necesarios
  exports: [UsuariosComponent], // Componentes exportados para otros módulos
})
export class UsuariosModule {}
