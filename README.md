# Portafolio de Esteban Oliveros

Sitio de una sola página para presentar servicios de desarrollo, proyectos, experiencia y un formulario de contacto. El formulario valida los datos localmente y muestra una confirmación; no transmite ni almacena la información.

## Tecnologías

- HTML5 semántico.
- Tailwind CSS 4 mediante Play CDN fijado a `@tailwindcss/browser@4.3.3`.
- JavaScript puro para menú, tema, navegación activa, acordeón, validación y toast.
- SVG propios almacenados en `assets/`.
- Google Fonts: Space Grotesk para títulos e Inter para texto; se usan fuentes de sistema como respaldo.

## Estructura de carpetas

```text
.
├── index.html
├── README.md
├── .nojekyll
└── assets/
    ├── avatar.svg
    ├── favicon.svg
    ├── hero.svg
    ├── icono-*.svg
    └── proyecto-*.svg
```

Las tarjetas del contenido están escritas directamente en `index.html` para que sea fácil editarlas sin JavaScript. No se añadieron fotografías ni recursos SVG externos.

## Abrir en local

Puedes abrir `index.html` directamente en el navegador. Para servirlo por HTTP desde la carpeta del proyecto, también puedes ejecutar:

```bash
npx serve .
```

El CSS de Tailwind, las fuentes y el CDN requieren conexión a internet. Los SVG propios y el HTML quedan en el proyecto.

## Decisiones de diseño

La interfaz sigue la distribución visual 60-30-10: superficies claras u oscuras para el fondo, verde profundo para las áreas de marca y amarillo cálido para llamadas a la acción y detalles. En modo oscuro se conservan los tonos de marca y acento; cambian superficies, texto, bordes y campos.

| Par de texto y fondo | Contraste indicado | Uso |
|---|---:|---|
| `#12372A` sobre `#F6F8F4` | 12.24:1 | Texto principal en modo claro |
| `#3F5A4E` sobre `#F6F8F4` | 7.06:1 | Texto secundario en modo claro |
| `#12372A` sobre `#E3A72F` | 6.13:1 | Texto de botones de acento |
| `#FFFFFF` sobre `#12372A` | 13.08:1 | Texto en hero, navbar y footer |
| `#FFFFFF` sobre `#146C43` | 6.45:1 | Confirmación del formulario |
| `#B42318` sobre `#F6F8F4` | 6.15:1 | Errores en modo claro |
| `#E8F0EA` sobre `#0E1714` | 15.71:1 | Texto principal en modo oscuro |
| `#A9BDB1` sobre `#16251F` | 8.04:1 | Texto secundario sobre panel oscuro |
| `#FDA29B` sobre `#16251F` | 8.20:1 | Errores en modo oscuro |

Tipografía: Space Grotesk (500 y 700) para títulos; Inter (400, 500 y 600) para texto. Breakpoints mobile-first de Tailwind: `sm` (640 px), `md` (768 px) y `lg` (1024 px). El contenedor principal llega a `max-w-6xl`; las secciones usan separación vertical adaptable y margen de desplazamiento para la navegación fija. Los valores de contraste anteriores corresponden a los pares definidos para el tema; los cambios posteriores de color deben volver a comprobarse.

## Accesibilidad aplicada

- Idioma `es-CO`, estructura semántica, un solo H1, título y descripción de página.
- Enlace para saltar al contenido, foco visible, etiquetas explícitas, controles con áreas táctiles amplias y navegación por teclado.
- SVG informativos con texto alternativo y SVG decorativos con texto alternativo vacío.
- Menú con estado ARIA, enlace actual de navegación, acordeón de panel único y errores textuales asociados con `aria-describedby`.
- Formulario con `aria-invalid`, foco en el primer campo inválido y región de confirmación viva.
- Modo oscuro con preferencia guardada o preferencia del sistema; preferencia de movimiento reducido para desplazamiento y transiciones.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub y agrega estos archivos a la rama que quieras publicar.
2. En el repositorio abre **Settings → Pages**.
3. En **Build and deployment**, selecciona **Deploy from a branch**, elige la rama y la carpeta raíz (`/`).
4. Guarda y espera a que Pages publique el sitio. El archivo `.nojekyll` está incluido en la raíz.
5. Abre la URL que GitHub Pages muestre y confirma que los recursos SVG carguen correctamente.

No se configuró un remoto ni se publicó el sitio.

## Verificación y pasos manuales

- `npx --yes html-validate index.html`: validación completada sin errores.
- Chromium 150 con Playwright 1.64.1: capturas y revisión a 375, 768 y 1280 px. El ancho del documento coincide con el viewport y no hay imágenes rotas.
- Chromium/Playwright: sin errores de consola ni excepciones; menú abre y cierra con Escape devolviendo el foco; el acordeón mantiene un panel abierto; el formulario enfoca el primer error y, al completar datos válidos, limpia los campos y presenta el toast.
- Lighthouse, categoría Accesibilidad: 100/100. No reportó auditorías binarias fallidas.

Para una revisión manual adicional, abre DevTools, activa el modo responsive (F12 → modo responsive) y comprueba 375 px, 768 px y 1280 px. También puedes revisar el HTML en <https://validator.w3.org/> y ejecutar Lighthouse en Chrome. No se han añadido resultados manuales adicionales.

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

El sitio se generó con ayuda de Codex a partir de un prompt maestro y fue revisado por el autor.
