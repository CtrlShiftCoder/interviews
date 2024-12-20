## Senior

### Ejercicio 4
**Crea un componente en Angular que se comunique con un backend (simulado) para enviar un formulario y mostrar un mensaje de éxito o error. Usa Reactive Forms y maneja el estado de la solicitud.**

**Respuesta:**

1. Primero, crea el componente usando Angular CLI:

```bash
ng generate component formulario

2. Instala HttpClientModule en el módulo:

app.module.ts:

import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { HttpClientModule } from '@angular/common/http';
import { ReactiveFormsModule } from '@angular/forms';
import { AppComponent } from './app.component';
import { FormularioComponent } from './formulario/formulario.component';

@NgModule({
  declarations: [
    AppComponent,
    FormularioComponent
  ],
  imports: [
    BrowserModule,
    HttpClientModule,
    ReactiveFormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

3. Crea el formulario reactivo en el componente:
formulario.component.ts:

import { Component } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Component({
  selector: 'app-formulario',
  templateUrl: './formulario.component.html',
  styleUrls: ['./formulario.component.css']
})
export class FormularioComponent {
  formulario: FormGroup;
  mensaje: string = '';
  loading: boolean = false;

  constructor(private fb: FormBuilder, private http: HttpClient) {
    this.formulario = this.fb.group({
      nombre: ['', [Validators.required, Validators.minLength(3)]],
      email: ['', [Validators.required, Validators.email]]
    });
  }

  enviarFormulario() {
    if (this.formulario.valid) {
      this.loading = true;
      this.http.post('https://jsonplaceholder.typicode.com/posts', this.formulario.value).subscribe(
        (response) => {
          this.mensaje = 'Formulario enviado con éxito';
          this.loading = false;
        },
        (error) => {
          this.mensaje = 'Hubo un error al enviar el formulario';
          this.loading = false;
        }
      );
    } else {
      this.mensaje = 'Por favor, completa el formulario correctamente';
    }
  }
}

formulario.component.html:

<div *ngIf="loading">Enviando...</div>
<div *ngIf="mensaje">{{ mensaje }}</div>

<form [formGroup]="formulario" (ngSubmit)="enviarFormulario()">
  <label for="nombre">Nombre</label>
  <input id="nombre" formControlName="nombre" />

  <label for="email">Email</label>
  <input id="email" formControlName="email" />

  <button type="submit" [disabled]="formulario.invalid">Enviar</button>
</form>