# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 4  
**¿Qué es un servicio en Angular y para qué se utiliza?**  

**Respuesta:**  
Un servicio en Angular es una clase que se utiliza para encapsular lógica o funcionalidad que puede ser compartida entre diferentes componentes. Los servicios son ideales para manejar lógica de negocio, interactuar con APIs, compartir datos entre componentes o realizar operaciones reutilizables.

**Ejemplo:**  
1. **Creación del servicio:**  
```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class UsuarioService {
  obtenerUsuarios(): string[] {
    return ['Juan', 'María', 'Carlos', 'Ana'];
  }
}
