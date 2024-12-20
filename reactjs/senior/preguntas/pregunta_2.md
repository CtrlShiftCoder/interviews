# Pruebas Técnicas para React con Respuestas y Ejemplos

## Senior

### Ejercicio 2
**Crea un formulario en React que permita a los usuarios registrarse proporcionando su nombre, correo electrónico y contraseña. Implementa la validación de los campos y muestra mensajes de error si los campos son incorrectos. Al enviar el formulario, simula el envío de los datos a una API y muestra un mensaje de éxito o error.**

**Respuesta:**

1. Crea un formulario con los campos `name`, `email` y `password`, implementa validaciones en cada campo y maneja el envío del formulario con un mensaje de éxito o error simulado.

**`RegistrationForm.js`**:
```javascript
import React, { useState } from 'react';

function RegistrationForm() {
  // Estado para los campos del formulario
  const [formData, setFormData] = useState({
    name: '',
    email: '',
    password: ''
  });
  
  // Estado para los mensajes de error
  const [errors, setErrors] = useState({
    name: '',
    email: '',
    password: ''
  });
  
  // Estado para el mensaje de éxito o error
  const [message, setMessage] = useState('');

  // Manejar cambios en los campos del formulario
  const handleChange = (e) => {
    const { name, value } = e.target;
    setFormData({
      ...formData,
      [name]: value
    });
  };

  // Validar los campos del formulario
  const validateForm = () => {
    let valid = true;
    let newErrors = { name: '', email: '', password: '' };

    // Validación para el nombre
    if (!formData.name) {
      newErrors.name = 'El nombre es obligatorio';
      valid = false;
    }

    // Validación para el correo electrónico
    if (!formData.email) {
      newErrors.email = 'El correo electrónico es obligatorio';
      valid = false;
    } else if (!/\S+@\S+\.\S+/.test(formData.email)) {
      newErrors.email = 'El correo electrónico no es válido';
      valid = false;
    }

    // Validación para la contraseña
    if (!formData.password) {
      newErrors.password = 'La contraseña es obligatoria';
      valid = false;
    } else if (formData.password.length < 6) {
      newErrors.password = 'La contraseña debe tener al menos 6 caracteres';
      valid = false;
    }

    setErrors(newErrors);
    return valid;
  };

  // Manejar el envío del formulario
  const handleSubmit = async (e) => {
    e.preventDefault();
    if (validateForm()) {
      // Simulación de envío de datos a una API
      setMessage('Registrando usuario...');

      // Simulando una API que devuelve éxito o error después de 2 segundos
      setTimeout(() => {
        // Simulación de respuesta de la API
        setMessage('¡Registro exitoso!'); // En caso de éxito
        // setMessage('Hubo un error al registrar el usuario'); // En caso de error
      }, 2000);
    } else {
      setMessage('');
    }
  };

  return (
    <div>
      <h2>Formulario de Registro</h2>
      <form onSubmit={handleSubmit}>
        <div>
          <label htmlFor="name">Nombre:</label>
          <input
            type="text"
            id="name"
            name="name"
            value={formData.name}
            onChange={handleChange}
          />
          {errors.name && <span style={{ color: 'red' }}>{errors.name}</span>}
        </div>

        <div>
          <label htmlFor="email">Correo Electrónico:</label>
          <input
            type="email"
            id="email"
            name="email"
            value={formData.email}
            onChange={handleChange}
          />
          {errors.email && <span style={{ color: 'red' }}>{errors.email}</span>}
        </div>

        <div>
          <label htmlFor="password">Contraseña:</label>
          <input
            type="password"
            id="password"
            name="password"
            value={formData.password}
            onChange={handleChange}
          />
          {errors.password && <span style={{ color: 'red' }}>{errors.password}</span>}
        </div>

        <button type="submit">Registrar</button>
      </form>

      {message && <p>{message}</p>}
    </div>
  );
}

export default RegistrationForm;
