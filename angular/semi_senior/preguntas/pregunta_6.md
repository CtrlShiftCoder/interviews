# Preguntas Técnicas para Angular con Respuestas y Ejemplos

## Semi Senior

### Pregunta 6  
**¿Qué es el `Router` en Angular y cómo se configura para navegar entre componentes?**

**Respuesta:**  
El `Router` en Angular es una herramienta que permite gestionar la navegación entre diferentes vistas o componentes dentro de una aplicación. Proporciona funcionalidades para definir rutas, navegar entre ellas y pasar parámetros de una ruta a otra. El `Router` utiliza un archivo de configuración de rutas donde se mapea una URL a un componente específico.

**Ejemplo:**  

1. **Configuración básica del `Router`:**

Primero, debes definir las rutas en un módulo de enrutamiento (`app-routing.module.ts`):

```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

const routes: Routes = [
  { path: '', component: HomeComponent }, // Ruta por defecto
  { path: 'about', component: AboutComponent }, // Ruta para AboutComponent
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule],
})
export class AppRoutingModule {}
