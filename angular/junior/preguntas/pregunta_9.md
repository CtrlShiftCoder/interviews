# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Junior

### Pregunta 9  
**¿Qué es un servicio en Angular y cómo se utiliza?**

**Respuesta:**  
Un servicio en Angular es una clase que contiene lógica reutilizable que se puede compartir entre diferentes componentes. Los servicios suelen utilizarse para gestionar datos, lógica empresarial o interactuar con APIs externas.  

**Ejemplo:**  

1. **Creación de un servicio:**  
```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root', // El servicio estará disponible en toda la aplicación
})
export class UsuarioService {
  private usuarios: string[] = ['Juan', 'Ana', 'Luis'];

  obtenerUsuarios(): string[] {
    return this.usuarios;
  }

  agregarUsuario(usuario: string): void {
    this.usuarios.push(usuario);
  }
}
