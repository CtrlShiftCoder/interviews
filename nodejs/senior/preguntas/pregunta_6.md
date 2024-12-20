# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 6  
**¿Qué es un Module en Angular y cómo se organiza una aplicación Angular utilizando módulos?**

**Respuesta:**  
Un **Module** en Angular es un contenedor que agrupa componentes, directivas, pipes y servicios relacionados. Los módulos ayudan a organizar el código y permiten cargar y administrar las funcionalidades de una aplicación de manera eficiente. Cada aplicación Angular tiene al menos un módulo: el **AppModule**.

**Ejemplo de un Module:**

1. **Definición de un módulo:**

```typescript
// src/app/app.module.ts
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';
import { UserService } from './user.service';

@NgModule({
  declarations: [AppComponent],  // Componentes, directivas y pipes
  imports: [BrowserModule],      // Módulos importados
  providers: [UserService],      // Servicios inyectados
  bootstrap: [AppComponent],     // Componente de inicio
})
export class AppModule {}
