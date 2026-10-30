# Mundo Umami

Guía editorial de gastronomía viajera con ideas para explorar restaurantes, mercados, comida callejera y experiencias culinarias fuera de lo común. Las rutas son conceptuales, no establecimientos verificados. El sitio combina fotografías reales de Unsplash descargadas a `assets/fotos/` con iconos SVG propios. El formulario valida localmente y muestra una confirmación sin transmitir ni guardar los datos.

## Tecnologías

- HTML5 semántico.
- Tailwind CSS 4 mediante Play CDN fijado a `@tailwindcss/browser@4.3.3`.
- JavaScript puro para navegación móvil, tema, secciones activas, acordeón, validación y toast.
- Fotografías locales de Unsplash y elementos vectoriales SVG creados para este proyecto.
- Google Fonts: Space Grotesk para títulos e Inter para texto, con fuentes de sistema como respaldo.

## Estructura de carpetas

```text
.
├── index.html
├── README.md
├── GUIA_DE_CAMBIOS.md
├── .nojekyll
└── assets/
    ├── PHOTO_CREDITS.md
    ├── favicon.svg
    ├── sello-mesa.svg
    ├── fotos/
    │   └── *.jpg
    └── icono-*.svg
```

Las tarjetas están escritas directamente en `index.html` para facilitar la edición. Las fotografías se guardan localmente y sus autores y páginas de origen están en [assets/PHOTO_CREDITS.md](assets/PHOTO_CREDITS.md).

## Abrir en local

Abre `index.html` en el navegador, o ejecuta desde esta carpeta:

```bash
npx serve .
```

El CDN de Tailwind y Google Fonts requieren conexión a internet. Las fotografías y los SVG están incluidos localmente en `assets/`.

## Decisiones de diseño

Tema editorial de sobremesa con reparto 60-30-10: superficies cálidas como base, ciruela profunda para las áreas de marca y mango para las llamadas a la acción. Las fotografías aportan escenas reales de puestos nocturnos, frutas, especias, fermentos, postres y cocina al fuego. Los iconos SVG conservan la identidad ilustrada del proyecto. En modo oscuro se conservan marca y acento mientras se adaptan superficies, texto, bordes y campos.

| Par de texto y fondo | Contraste calculado | Uso |
|---|---:|---|
| `#321C35` sobre `#FFF7ED` | 14.62:1 | Texto principal claro |
| `#66536B` sobre `#FFF7ED` | 6.56:1 | Texto secundario claro |
| `#30183D` sobre `#F7B84B` | 9.00:1 | Texto de botones de acento |
| `#FFFFFF` sobre `#30183D` | 15.86:1 | Texto en hero, navegación y pie |
| `#FFFFFF` sobre `#146C43` | 6.45:1 | Confirmación del formulario |
| `#B42318` sobre `#FFF7ED` | 6.19:1 | Errores en modo claro |
| `#F5EEF5` sobre `#17121B` | 16.18:1 | Texto principal oscuro |
| `#C5B5C9` sobre `#241B2A` | 8.56:1 | Texto secundario sobre panel oscuro |
| `#FDA29B` sobre `#241B2A` | 8.55:1 | Errores en modo oscuro |

Tipografía: Space Grotesk (500 y 700) en títulos; Inter (400, 500 y 600) para textos. El diseño es mobile-first y usa los breakpoints `sm` (640 px), `md` (768 px) y `lg` (1024 px). Se conserva un contenedor de hasta `max-w-6xl`, secciones con espacio adaptable y `scroll-mt-20` por la navegación fija. Los contrastes se calcularon con la fórmula WCAG; deben volver a revisarse si se cambian los colores.

## Accesibilidad aplicada

- `lang="es-CO"`, jerarquía semántica, un H1 y enlace para saltar al contenido.
- Foco visible, labels asociados, controles táctiles amplios y navegación por teclado.
- Fotografías informativas con texto alternativo; iconos decorativos ocultos a lectores de pantalla.
- Menú móvil con estados ARIA, enlaces activos y acordeón de panel único.
- Formulario con errores asociados, `aria-invalid` y foco en el primer campo inválido.
- Preferencia de tema guardada en `localStorage` con respaldo del sistema; movimiento reducido respetado.
- Las rutas están identificadas como ideas conceptuales; las fotografías tienen texto alternativo y crédito en `assets/PHOTO_CREDITS.md`.
- Las imágenes se sirven desde el propio proyecto; el único CDN de contenido visual es Google Fonts para tipografía.

## Publicar en GitHub Pages

1. Sube los archivos a la rama del repositorio que quieras publicar.
2. En GitHub abre **Settings → Pages**.
3. Selecciona **Deploy from a branch**, elige la rama y la carpeta raíz (`/`).
4. Guarda y espera a que Pages publique el sitio. `.nojekyll` ya está en la raíz.
5. Abre la URL publicada y revisa las fotografías y el formulario en móvil y escritorio.

No se configuró un remoto ni se publicó el sitio.

## Verificación y pasos manuales

- `npx --yes html-validate index.html`: pasó sin errores.
- Chromium con Playwright: revisé 375, 768 y 1280 px; no hay desbordamiento horizontal ni imágenes rotas.
- Revisé menú, acordeón, validación y envío local de demostración del formulario y cambio de tema; sin errores de consola.
- Lighthouse, categoría Accesibilidad: 100/100, sin auditorías binarias fallidas.

Para una revisión manual adicional, abre DevTools, activa modo responsive (F12 → modo responsive) y revisa esos tres anchos. También puedes validar en <https://validator.w3.org/>.

## Prompt maestro

(pegar aquí la versión 1)

## Bitácora de prompts

| # | Prompt de ajuste enviado | Problema que buscaba resolver | Resultado obtenido | ¿Funcionó? |
|---|---|---|---|---|
| 1 | (pendiente) | (pendiente) | (pendiente) | (pendiente) |
| 2 | (pendiente) | (pendiente) | (pendiente) | (pendiente) |
| 3 | (pendiente) | (pendiente) | (pendiente) | (pendiente) |
| 4 | (pendiente) | (pendiente) | (pendiente) | (pendiente) |
| 5 | (pendiente) | (pendiente) | (pendiente) | (pendiente) |

## Cambios manuales (sin IA)

- (pendiente)
- (pendiente)
- (pendiente)

## Uso de IA

El sitio se generó con ayuda de Codex a partir de instrucciones de diseño y fue revisado por el autor. Para entenderlo y practicar tres ediciones sencillas, consulta [GUIA_DE_CAMBIOS.md](GUIA_DE_CAMBIOS.md).
