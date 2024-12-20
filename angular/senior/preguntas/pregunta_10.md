# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Senior

### Pregunta 10  
**¿Qué es el Router en Angular y cómo se utiliza para navegar entre componentes?**

**Respuesta:**  
El **Router** en Angular es un módulo que permite navegar entre diferentes vistas o componentes dentro de una aplicación de una sola página (SPA). El router gestiona la navegación entre las rutas configuradas y permite que los usuarios naveguen entre las distintas partes de la aplicación sin recargar la página.

El router se configura en el módulo de la aplicación a través de las rutas y se usa con la directiva `routerLink` para navegar entre componentes.

**Ejemplo de configuración del Router:**

1. **Definir las rutas en el archivo de configuración:**

```typescript
// src/app/app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule {}
