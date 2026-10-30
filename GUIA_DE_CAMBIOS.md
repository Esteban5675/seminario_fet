# Guía del proyecto y tres cambios manuales

## ¿Qué es Mundo Umami?

Mundo Umami es una página estática de una sola vista. Presenta ideas para una guía gastronómica: restaurantes, mercados, comida callejera y otros planes culinarios. Las seis rutas de la página son propuestas conceptuales; no son fichas de negocios reales ni incluyen precios, horarios o direcciones.

La página sirve como práctica de HTML semántico, diseño responsive con Tailwind CSS 4 y JavaScript sin frameworks. Tiene navegación móvil, modo claro/oscuro, enlaces activos, FAQ tipo acordeón y un formulario validado. El formulario solo funciona dentro del navegador: no envía información a un servidor.

## ¿Cómo está organizado?

- `index.html`: contiene todo el contenido, estilos de Tailwind, interacciones y formulario.
- `assets/fotos/`: fotografías reales usadas en el hero y las tarjetas.
- `assets/PHOTO_CREDITS.md`: autor y página de origen para cada fotografía.
- `assets/icono-*.svg`, `sello-mesa.svg` y `favicon.svg`: iconos y marca en formato vectorial.
- `README.md`: tecnologías, diseño, accesibilidad, verificación y publicación.
- `.nojekyll`: permite publicar la carpeta directamente con GitHub Pages.

## Antes de editar

1. Haz una copia del archivo que vas a cambiar o usa Git para poder deshacer el cambio.
2. Abre `index.html` en un editor de texto.
3. Busca el texto o el `id` indicado en cada ejercicio con `Ctrl+F`.
4. Guarda el archivo y recarga la página en el navegador.

## Cambio 1: editar un título o una descripción

**Dificultad: fácil.** Busca `id="titulo-inicio"` para cambiar el titular principal, o busca `id="titulo-proyectos"` para cambiar el título de las rutas. El texto está dentro de una etiqueta HTML, por ejemplo:

```html
<h2 id="titulo-proyectos" class="...">Una mesa fuera de lo común</h2>
```

Reemplaza solo las palabras entre `>` y `<`, sin borrar las etiquetas ni el atributo `id`. Prueba un titular propio y revisa que se entienda en móvil.

## Cambio 2: reemplazar una fotografía

**Dificultad: fácil.** Escoge una foto con permiso de uso, descárgala y guárdala dentro de `assets/fotos/` con un nombre sencillo, por ejemplo `mi-restaurante.jpg`. En `index.html`, busca `src="assets/fotos/mercado-frutas.jpg"` y cambia la ruta por `src="assets/fotos/mi-restaurante.jpg"`.

También cambia el `alt` de esa misma etiqueta `<img>` para describir lo que se ve en la nueva foto. Conserva el crédito: agrega autor y enlace de origen a `assets/PHOTO_CREDITS.md`. No uses una foto como si mostrara un establecimiento distinto del que realmente aparece.

## Cambio 3: ajustar los colores de la página

**Dificultad: fácil.** En `index.html`, dentro de `<style type="text/tailwindcss">`, busca `@theme`. Allí están los tokens de color:

```css
--color-brand: #30183D;
--color-accent: #F7B84B;
```

Cambia primero esos dos valores para probar una nueva combinación. `brand` se usa en la navegación, el hero y el pie de página; `accent` se usa en botones y detalles. Mantén texto claro sobre fondos oscuros y texto oscuro sobre los botones. Comprueba el contraste con un verificador WCAG antes de dejar tus nuevos colores.

## Abrir y revisar

Puedes abrir `index.html` directamente o ejecutar `npx serve .` desde la carpeta del proyecto. Para revisar la adaptación, prueba 375 px, 768 px y 1280 px en el modo responsive del navegador. Si algo no se ve bien, deshaz el último cambio y prueba de nuevo una sola modificación.

## Límites de esta demo

El formulario no guarda ni transmite mensajes. Los lugares y planes son conceptos editoriales, no recomendaciones de establecimientos específicos. Para publicar una guía comercial habría que añadir datos verificados, autorización para mostrar negocios, un servicio de formulario y un proceso para mantener la información actualizada.
