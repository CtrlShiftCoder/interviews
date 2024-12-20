# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 5  
**¿Qué es un Service en Angular y cómo se utiliza para la inyección de dependencias?**

**Respuesta:**  
Un **Service** en Angular es una clase utilizada para compartir lógica de negocio o funcionalidades comunes entre diferentes componentes de la aplicación. Los servicios se utilizan para manejar operaciones como acceder a una API, realizar cálculos, gestionar el estado, entre otros. Angular utiliza la **inyección de dependencias** para inyectar servicios en los componentes de manera automática.

**Ejemplo de un Service:**

1. **Creación de un Service:**

```typescript
// src/app/user.service.ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root', // Esto asegura que el servicio es singleton y está disponible globalmente
})
export class UserService {
  constructor() {}

  getUser() {
    return { name: 'John Doe', age: 30 };
  }
}
