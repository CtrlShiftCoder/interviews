# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 3  
**¿Qué es Lazy Loading en Angular y cómo mejora el rendimiento de una aplicación?**

**Respuesta:**  
**Lazy Loading** en Angular es una técnica para cargar módulos de forma perezosa, es decir, solo cuando se necesiten. En lugar de cargar toda la aplicación al inicio, Angular carga los módulos solo cuando se navega a la ruta correspondiente. Esto mejora el rendimiento de la aplicación, ya que reduce el tamaño inicial de la carga.

**Ejemplo de implementación:**

1. **Configurar Lazy Loading en las rutas:**

En el archivo de rutas, podemos definir un módulo que se cargará de manera perezosa usando el `loadChildren`.

```typescript
// src/app/app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';

const routes: Routes = [
  {
    path: 'feature',
    loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule)
  },
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
