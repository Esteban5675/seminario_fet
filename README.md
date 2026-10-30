# Mundo Umami

Mundo Umami es una guía gastronómica editorial de una sola página. Reúne ideas para explorar restaurantes, mercados, comida callejera y experiencias culinarias. Las seis rutas son conceptos para inspirar planes; no son fichas ni recomendaciones verificadas de negocios reales.

El sitio usa fotografías reales descargadas localmente, con sus autores y enlaces de origen registrados en [assets/PHOTO_CREDITS.md](assets/PHOTO_CREDITS.md). El formulario valida datos en el navegador y enseña una confirmación de demostración: no envía ni guarda mensajes.

## Contenido del proyecto

- **Inicio:** presenta la guía y permite ir a restaurantes o experiencias.
- **Explorar:** seis categorías, como restaurantes, mercados, talleres y degustaciones.
- **Restaurantes y rutas:** seis planes conceptuales acompañados por fotografías.
- **La guía:** explica el propósito editorial y cómo interpretar las rutas.
- **Preguntas frecuentes:** acordeón que permite abrir una pregunta a la vez.
- **Contacto:** formulario de demostración con validación accesible.
- **Pie de página:** navegación, recordatorio de confirmar los datos con cada establecimiento y año automático.

## Tecnologías

- HTML5 semántico.
- Tailwind CSS 4 mediante Play CDN fijado a `@tailwindcss/browser@4.3.3`.
- JavaScript puro para el menú móvil, tema claro/oscuro, navegación activa, FAQ, formulario y toast.
- Siete fotografías locales de Unsplash, más iconos y marca en SVG.
- Google Fonts: Space Grotesk para títulos e Inter para textos, con respaldo de fuentes de sistema.

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
    │   ├── hero-restaurante.jpg
    │   ├── especias-mercado.jpg
    │   ├── mercado-frutas.jpg
    │   ├── puesto-nocturno.jpg
    │   ├── fermentos.jpg
    │   ├── postre.jpg
    │   └── cocina-al-fuego.jpg
    └── icono-*.svg
```

Las tarjetas están escritas directamente en `index.html` para que se puedan editar sin generar contenido con JavaScript. El archivo `assets/PHOTO_CREDITS.md` documenta las fotografías, autores y páginas de origen.

## Abrir en local

Abre `index.html` en el navegador, o inicia un servidor local desde la carpeta del proyecto:

```bash
npx serve .
```

El servidor mostrará la dirección local donde quedó disponible la página. Tailwind Play CDN y Google Fonts requieren conexión a internet. Las fotos y los SVG se cargan desde el mismo proyecto.

## Decisiones de diseño

La paleta sigue una proporción visual 60-30-10: superficies cálidas para el fondo, ciruela profunda para navegación, hero y pie, y mango para botones y detalles. El verde jade y el tono guayaba aparecen en los SVG decorativos. En modo oscuro se conservan marca y acento, y se adaptan superficies, texto y bordes.

La tipografía es Space Grotesk (500 y 700) para títulos e Inter (400, 500 y 600) para textos. El diseño es mobile-first y utiliza los breakpoints `sm` (640 px), `md` (768 px) y `lg` (1024 px), un contenedor de hasta `max-w-6xl` y `scroll-mt-20` para que los títulos no queden cubiertos por la navegación fija.

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

Los valores se calcularon con la fórmula de contraste WCAG. Si cambias los tokens de color, vuelve a comprobarlos antes de publicar.

## Accesibilidad y comportamiento

- Idioma `es-CO`, un único H1, estructura semántica y enlace para saltar al contenido.
- Texto alternativo descriptivo en fotografías y `alt=""` en iconos decorativos.
- Foco visible, navegación por teclado, áreas táctiles amplias y etiquetas asociadas a los campos.
- Menú móvil con `aria-expanded`, Escape, cierre al hacer clic fuera, seleccionar un enlace o ampliar la ventana.
- Enlace activo actualizado según la sección visible.
- Acordeón de panel único y controles con `aria-controls` y `aria-expanded`.
- Errores del formulario con texto, `aria-invalid`, `aria-describedby` y foco en el primer campo inválido.
- Toast de confirmación con región viva, cierre manual y cierre automático a los cuatro segundos.
- Preferencia de tema guardada en `localStorage`; si no existe, se respeta el tema del sistema. Se considera `prefers-reduced-motion`.
- Las rutas están identificadas como ideas conceptuales; no se inventan establecimientos, precios, direcciones, reseñas ni horarios.

## Fotografías y créditos

Las fotos se guardaron en `assets/fotos/` para que el sitio no dependa de cargar imágenes desde Unsplash al abrirlo. Consulta [assets/PHOTO_CREDITS.md](assets/PHOTO_CREDITS.md) para ver cada autor y la página de origen. Al reemplazar una foto, actualiza también su texto alternativo y ese archivo de créditos.

## Verificación realizada

- `npx --yes html-validate index.html`: pasó sin errores.
- Chromium con Playwright: revisé 375, 768 y 1280 px; el ancho del documento coincidió con el viewport y cargaron las fotos e iconos.
- Comprobé menú con Escape y retorno del foco, acordeón de panel único, foco en el primer error, envío local del formulario, limpieza de campos y cambio de tema. No hubo errores de consola.
- Lighthouse, categoría Accesibilidad: 100/100; no reportó auditorías binarias fallidas.

Para repetir la revisión responsive, abre las herramientas de desarrollo del navegador, activa el modo responsive y prueba esos tres anchos. También puedes validar el documento en <https://validator.w3.org/>.

## Publicar en GitHub Pages

GitHub Pages todavía no está activado para este repositorio. El repositorio está en [github.com/Esteban5675/seminario_fet](https://github.com/Esteban5675/seminario_fet), con la rama `main`. Para activar GitHub Pages:

1. Abre **Settings → Pages** en el repositorio.
2. En **Build and deployment**, selecciona **Deploy from a branch**.
3. Elige la rama `main` y la carpeta raíz (`/`), y guarda.
4. Cuando GitHub muestre la URL publicada, ábrela y revisa el sitio en escritorio y móvil.

El archivo `.nojekyll` ya está en la raíz. Después de activar Pages, GitHub mostrará la dirección pública del sitio en esa misma sección.

## Prompt maestro

> Crea y mantén una página web estática de una sola página llamada **Mundo Umami**, una guía editorial de gastronomía viajera sobre restaurantes, mercados, comida callejera y experiencias culinarias. No incluyas portafolios ni datos personales. Escribe en español de Colombia, con tono claro y cercano.
>
> Usa HTML5, Tailwind CSS 4 mediante Play CDN fijado a `https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4.3.3` y JavaScript puro. No añadas frameworks ni librerías. Conserva diseño mobile-first, landmarks semánticos, un solo H1, navegación por anclas, menú móvil accesible, modo claro/oscuro, navegación activa, FAQ de panel único y formulario accesible con validación en navegador. Respeta foco visible, movimiento reducido y contraste WCAG AA.
>
> Presenta rutas gastronómicas conceptuales claramente marcadas como ideas, no como negocios reales. No inventes establecimientos, direcciones, precios, horarios, reseñas ni datos de contacto. Usa fotografías reales guardadas localmente en `assets/fotos/`, con texto alternativo fiel a lo que muestran y créditos de autor y origen en `assets/PHOTO_CREDITS.md`. Mantén iconos y marca como SVG propios.
>
> Incluye `README.md` completo y `GUIA_DE_CAMBIOS.md` con tres ejercicios manuales sencillos: editar un texto, reemplazar una foto actualizando `alt` y créditos, y cambiar tokens de color comprobando contrastes. Verifica HTML, fotos, comportamiento del menú, FAQ y formulario; reporta solo resultados realmente comprobados.

## Bitácora de prompts

Los prompts están resumidos para documentar el proceso; no son transcripciones literales.

| # | Prompt de ajuste enviado | Problema que buscaba resolver | Resultado obtenido | ¿Funcionó? |
|---|---|---|---|---|
| 1 | Convierte la página en una guía de gastronomía y quita la presentación personal. | El contenido inicial no correspondía a la nueva temática deseada. | La página pasó a llamarse Mundo Umami y dejó de mostrar datos personales. | Sí |
| 2 | Explora una estética más exótica e incluye restaurantes, mercados y planes culinarios. | Faltaban una identidad visual distinta y variedad de experiencias. | Se diseñaron secciones de exploración y seis rutas temáticas. | Sí |
| 3 | Cambia las ilustraciones de las rutas por fotografías reales y guarda los créditos. | Las tarjetas no tenían el aspecto fotográfico solicitado ni fuentes documentadas. | Se añadieron siete fotos locales, textos alternativos y créditos de origen. | Sí |
| 4 | Explica el proyecto y propón tres cambios sencillos que pueda hacer manualmente. | Hacía falta una guía práctica para entender y editar el sitio. | Se creó `GUIA_DE_CAMBIOS.md` con ejercicios para editar texto, fotos y colores. | Sí |
| 5 | Completa el README con el propósito, estructura, decisiones de diseño, pruebas y registro del proceso. | La documentación tenía marcadores pendientes y datos incompletos. | Se completaron las secciones, la bitácora y los pasos de publicación. | Sí |

## Cambios manuales (sin IA)

- Cambia el titular de inicio buscando `id="titulo-inicio"` en `index.html`.
- Reemplaza una foto en `assets/fotos/` y actualiza su `src`, `alt` y crédito en `assets/PHOTO_CREDITS.md`.
- Prueba otra combinación de ciruela y mango modificando `--color-brand` y `--color-accent` dentro de `@theme`; después comprueba sus contrastes.

La explicación paso a paso está en [GUIA_DE_CAMBIOS.md](GUIA_DE_CAMBIOS.md).

## Uso de IA

Codex ayudó a estructurar y redactar el sitio, producir los SVG y preparar la guía. Las fotografías son recursos de terceros y están atribuidas en `assets/PHOTO_CREDITS.md`. El HTML, la carga de recursos, los flujos principales y los anchos indicados se verificaron en Chromium; la evaluación de accesibilidad de Lighthouse dio 100/100. El formulario sigue siendo una demostración local y no transmite mensajes.
