# PROMPTS.md - Documentación de Prompts utilizados con IA

## 1. Prompt Inicial/Base

### Prompt:
"Actúa como experto React. Necesito un componente que consuma https://jsonplaceholder.typicode.com/posts, muestre lista en grid con Bootstrap 5, colores acorde a la App. Implementa operaciones: agregar post local, editar, eliminar, persistir en Local Storage. Incluye validación de campos vacíos y manejo de errores con fetch. Dame el código con buenas prácticas de seguridad."

### Respuesta de IA:
La IA generó una estructura completa de componentes React:
- `App.js` como componente principal
- `PostGrid.jsx` para mostrar el grid
- `PostCard.jsx` para cada publicación
- `PostForm.jsx` para crear/editar
- `api.js` para consumir la API
- `useLocalStorage.js` para persistencia
- `validators.js` para validaciones

### Implementación:
- Se crearon todos los componentes sugeridos
- Se implementó Bootstrap 5 para el diseño
- Se agregó la funcionalidad CRUD completa
- Se integró Local Storage para persistencia

---

## 2. Prompt para Mejorar la Seguridad

### Prompt:
"¿Cómo puedo mejorar la seguridad de mi aplicación React? Específicamente en el manejo de datos del usuario y prevención de XSS al renderizar contenido de la API."

### Sugerencia de IA:
- Implementar una función `sanitizeHTML` para escapar caracteres peligrosos
- Validar todos los inputs del usuario antes de guardarlos
- Evitar el uso de `dangerouslySetInnerHTML`
- Usar validación en tiempo real en el formulario

### Implementación:
- Se creó `sanitizeHTML` en `validators.js`
- Se aplicó sanitización en `PostCard.jsx`
- Se implementaron validaciones `isValidTitle` e `isValidBody`
- El formulario valida en tiempo real con feedback visual

---

## 3. Prompt para Manejo de Errores
### Prompt:
"¿Cuál es la mejor práctica para manejar errores en una aplicación React que consume una API externa y usa Local Storage?"

### Sugerencia de IA:
- Usar bloques try...catch en todas las operaciones asíncronas
- Implementar un mecanismo de fallback: si la API falla, usar datos de Local Storage
- Mostrar mensajes de error específicos y amigables para el usuario
- Incluir estados de carga (loading) para mejorar la UX

### Implementación:
- Se agregó try...catch en fetchPosts y en loadPosts
- Se implementó fallback a Local Storage cuando la API falla
- Se crearon estados error y loading en App.js
- Se muestran mensajes de error específicos en la UI

---

## 4. Prompt para UX/UI

### Prompt:
"Sugiere mejoras de experiencia de usuario para mi aplicación de gestión de posts."

### Sugerencia de IA:
- Usar tarjetas con sombras y efectos hover
- Implementar feedback visual para todas las acciones
- Mantener una paleta de colores consistente
- Añadir iconos de Bootstrap para mejorar la comunicación visual
- Validación en tiempo real

### Implementación:
- Se agregaron clases CSS para efectos hover en tarjetas
- Se implementó feedback visual con clases is-invalid
- Se usó paleta de colores de Bootstrap (bg-primary, text-white)
- Se añadieron iconos de Bootstrap Icons
- Se incluyó spinner de carga y mensajes de feedback

---

## 5. Prompt para Contenido en Español
### Prompt:
"Quiero que me actualices los códigos para que muestren los textos en español que puedan ser customizados por mi."

### Sugerencia de IA:
- Crear un array de publicaciones personalizadas en español
- Mantener la estructura original de la API (userId, id, title, body)
- Organizar por temáticas

### Implementación:
- Se creó spanishPosts en api.js con 40 publicaciones
- Cada publicación incluye emojis y contenido