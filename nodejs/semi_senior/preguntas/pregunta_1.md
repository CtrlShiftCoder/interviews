# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 1  
**¿Qué es un `Resolver` en Angular y cuándo se utiliza?**

**Respuesta:**  
Un `Resolver` en Angular es una interfaz utilizada para obtener datos antes de que se cargue un componente. Esto permite que los datos necesarios estén disponibles en el momento en que el componente se inicializa, lo que puede ser útil para mejorar la experiencia del usuario al evitar cargar datos después de que el componente ya esté en la pantalla.

**Ejemplo:**  

1. **Creación de un Resolver:**  
```typescript
import { Injectable } from '@angular/core';
import { ActivatedRouteSnapshot, Resolve, RouterStateSnapshot } from '@angular/router';
import { Observable } from 'rxjs';
import { UsuarioService } from './usuario.service';
import { Usuario } from './usuario.model';

@Injectable({
  providedIn: 'root',
})
export class UsuarioResolver implements Resolve<Usuario> {
  constructor(private usuarioService: UsuarioService) {}

  resolve(route: ActivatedRouteSnapshot, state: RouterStateSnapshot): Observable<Usuario> {
    const id = route.paramMap.get('id');
    return this.usuarioService.obtenerUsuarioPorId(id);
  }
}
