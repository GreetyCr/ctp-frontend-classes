# Práctica 3: Formulario de Registro Avanzado

## Objetivo
Crear un formulario de registro completo e interactivo utilizando HTML5, implementando validación nativa y diversos controles de formulario.

## Descripción
En esta práctica desarrollarás un formulario de registro para una plataforma educativa ficticia. Deberás implementar diferentes tipos de inputs, agrupación de campos, validación nativa HTML5, y características de accesibilidad.

## Requisitos
1. Implementar un formulario completo con los siguientes grupos de campos:
   - Información personal
   - Datos académicos
   - Preferencias de la plataforma
   - Términos y condiciones

2. Utilizar correctamente los siguientes elementos:
   - `<form>` con atributos adecuados
   - `<fieldset>` y `<legend>` para agrupar campos relacionados
   - `<label>` correctamente vinculados a cada input
   - Atributo `placeholder` donde sea apropiado
   - Atributo `required` para campos obligatorios
   - Otros atributos de validación como `pattern`, `min`, `max`, etc.

3. Implementar al menos 12 tipos diferentes de controles de formulario:
   - Campos de texto simples (`text`)
   - Correo electrónico (`email`) con validación
   - Contraseña (`password`) con requisitos de longitud
   - Fecha (`date`)
   - Número (`number`) con rango
   - Teléfono (`tel`) con patrón
   - URL (`url`)
   - Selección desplegable (`select` con `option`)
   - Casillas de verificación múltiple (`checkbox`)
   - Botones de radio (`radio`)
   - Selector de color (`color`)
   - Rango (`range`) con `datalist`
   - Área de texto (`textarea`)
   - Carga de archivos (`file`) con restricciones

4. Incluir características de accesibilidad:
   - Atributos `aria-` donde sea necesario
   - Uso de `tabindex` para controlar el orden de tabulación
   - Textos descriptivos para asistencia
   - Elementos `<output>` para mostrar resultados

## Estructura del Formulario

### 1. Información Personal
- Nombre completo (obligatorio)
- Correo electrónico (obligatorio, validación)
- Contraseña (obligatorio, mínimo 8 caracteres)
- Confirmación de contraseña
- Fecha de nacimiento (con restricción de edad mínima)
- Número de teléfono (formato específico)
- Dirección (calle, ciudad, código postal)
- Foto de perfil (selector de archivo, solo imágenes)

### 2. Datos Académicos
- Nivel de estudios (botones de radio)
- Áreas de interés (casillas de verificación múltiple)
- Universidad/Institución (campo de texto)
- URL del portfolio/LinkedIn (validación de URL)
- Nivel de idiomas (inglés, español, otro) usando rango o select

### 3. Preferencias de la Plataforma
- Tema de color preferido (selector de color)
- Notificaciones (opciones con checkbox)
- Privacidad del perfil (opciones con radio)
- Frecuencia de correos (selector con opciones)
- Zona horaria (selector con opciones)

### 4. Términos y Condiciones
- Aceptación de términos (checkbox obligatorio)
- Suscripción al boletín (checkbox opcional)
- Verificación de no ser robot (checkbox con pregunta simple)

### 5. Botones de Acción
- Enviar formulario
- Restablecer formulario (con advertencia)

## Validación y Feedback
- Utilizar atributos de validación nativa HTML5
- Mensajes personalizados mediante el atributo `title`
- Indicación visual clara de campos obligatorios
- Feedback instantáneo al usuario

## Consejos
- Diseña primero la estructura general del formulario antes de implementar
- Utiliza indentación consistente para mantener el código legible
- Agrupa campos relacionados usando `fieldset`
- Añade comentarios para explicar secciones complejas
- Prueba el formulario en diferentes navegadores

## Entrega
1. Archivo HTML con el formulario completo
2. Documento breve explicando:
   - Tipos de inputs utilizados y por qué
   - Estrategias de validación implementadas
   - Consideraciones de accesibilidad
   - Retos encontrados y soluciones

## Criterios de Evaluación
- Implementación correcta de todos los tipos de control requeridos
- Uso adecuado de validación nativa HTML5
- Organización lógica y agrupación de campos
- Accesibilidad del formulario
- Claridad y legibilidad del código
- Validez del HTML (verificable en validadores W3C)
- Funcionalidad completa del formulario 