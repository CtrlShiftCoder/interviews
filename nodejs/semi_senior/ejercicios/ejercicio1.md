## Semi Senior

### Ejercicio 1
**Crea un formulario en Angular que permita ingresar un nombre y una edad, y luego mostrar un mensaje de bienvenida con el nombre y la edad cuando se envíe el formulario.**

**Respuesta:**

1. Crea el componente usando Angular CLI:

```bash
ng generate component formulario


2. Luego, edita los archivos generados:
formulario.component.ts:

import { Component } from '@angular/core';

@Component({
  selector: 'app-formulario',
  templateUrl: './formulario.component.html',
  styleUrls: ['./formulario.component.css']
})
export class FormularioComponent {
  nombre: string = '';
  edad: number | null = null;
  mensaje: string = '';

  onSubmit() {
    if (this.nombre && this.edad) {
      this.mensaje = `Bienvenido, ${this.nombre}. Tienes ${this.edad} años.`;
    } else {
      this.mensaje = 'Por favor, completa todos los campos.';
    }
  }
}

formulario.component.html:


<form (ngSubmit)="onSubmit()">
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" [(ngModel)]="nombre" name="nombre" required>

  <label for="edad">Edad:</label>
  <input type="number" id="edad" [(ngModel)]="edad" name="edad" required>

  <button type="submit">Enviar</button>
</form>

<p>{{ mensaje }}</p>


app.module.ts (Asegúrate de importar FormsModule para poder usar ngModel):

import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from '@angular/forms'; // Importa FormsModule

import { AppComponent } from './app.component';
import { FormularioComponent } from './formulario/formulario.component';

@NgModule({
  declarations: [
    AppComponent,
    FormularioComponent
  ],
  imports: [
    BrowserModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }