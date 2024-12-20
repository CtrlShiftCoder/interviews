# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 7  
**¿Qué es un Guard en Angular y cómo se utiliza para la protección de rutas?**

**Respuesta:**  
Un **Guard** en Angular es una interfaz que se utiliza para proteger las rutas y controlar el acceso a diferentes secciones de una aplicación. Los guards permiten decidir si una ruta puede ser activada, desactivada o si se puede acceder a ella según ciertas condiciones, como la autenticación o la autorización del usuario.

**Tipos de Guards:**
1. **CanActivate**: Controla si una ruta puede ser activada.
2. **CanActivateChild**: Controla si una ruta hija puede ser activada.
3. **CanDeactivate**: Controla si el usuario puede abandonar una ruta.
4. **Resolve**: Permite pre-cargar datos antes de activar la ruta.

**Ejemplo de uso de un Guard:**

1. **Creación de un Guard (CanActivate):**

```typescript
// src/app/auth/auth.guard.ts
import { Injectable } from '@angular/core';
import { CanActivate, ActivatedRouteSnapshot, RouterStateSnapshot, Router } from '@angular/router';
import { Observable } from 'rxjs';
import { AuthService } from './auth.service';

@Injectable({
  providedIn: 'root',
})
export class AuthGuard implements CanActivate {
  constructor(private authService: AuthService, private router: Router) {}

  canActivate(
    route: ActivatedRouteSnapshot,
    state: RouterStateSnapshot
  ): Observable<boolean> | Promise<boolean> | boolean {
    if (this.authService.isLoggedIn()) {
      return true;
    } else {
      this.router.navigate(['/login']);
      return false;
    }
  }
}
