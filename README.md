# mi-portafolio

Sitio web de portafolio personal de **Jorge Meléndez**, construido para el curso
**BIOS — "Desarrollo de Software Aumentado con IA"**.

Es una página de una sola vista (single-page) con secciones enlazadas por anclas:
**Sobre mí**, **Proyectos** y **Contacto**.

## Características

- **Solo HTML y CSS.** Sin JavaScript, frameworks, ni herramientas de build. Cero dependencias.
- **Diseño tranquilo.** Sin animaciones, transiciones ni elementos en movimiento; estático y predecible.
- **Paleta sobria** de 4 colores apagados definidos como variables `:root` en `css/base.css`.
- **Accesible.** Tipografía ≥16px, `line-height: 1.6`, jerarquía de encabezados clara y espaciado generoso.

## Estructura

```
index.html        # Punto de entrada: header, nav y secciones #about, #projects, #contact + footer
css/
  base.css        # Reset, variables :root (paleta, fuentes, espaciado), estilos base
  layout.css      # Header, nav, contenedores de sección, footer, responsive (@media)
  components.css  # Piezas reutilizables: tarjetas de proyecto, lista de contacto
assets/
  images/         # Fotos e imágenes decorativas
  icons/          # Iconos SVG, favicon
```

> **El orden de carga del CSS importa:** `base.css` → `layout.css` → `components.css`,
> para que las variables y la cascada se resuelvan de forma predecible.

## Cómo ejecutarlo

No requiere instalación ni paso de build. Elige una opción:

- Por medio de la siguiente URL: https://jorgeelopezm.github.io/mi-portafolio/
- Abre `index.html` directamente en el navegador (doble clic).
- O sírvelo con un servidor estático, por ejemplo:

  ```bash
  python -m http.server 8000
  ```

  y visita `http://localhost:8000`.

## Despliegue

El sitio se publica en **GitHub Pages**. En la rama `main`, GitHub Pages sirve `index.html`
desde la raíz del repositorio.

## Paleta

| Uso                    | Color      |
| ---------------------- | ---------- |
| Fondo (crema)          | `#f4efe6`  |
| Texto (gris cálido)    | `#36352f`  |
| Encabezados / enlaces  | `#5e7a8a`  |
| Acentos / bordes       | `#8a9a82`  |
| Superficie de tarjetas | `#ede7da`  |

## Licencia

Proyecto educativo. © 2026 Jorge Meléndez.
