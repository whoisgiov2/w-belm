# w-belm

> **Web Elements & Micro-interactions Library**  
> Colección modular de componentes interactivos, widgets flotantes y micro-interacciones de alto rendimiento para tiendas **Shopify (Online Store 2.0)** y aplicaciones web modernas.

[![Shopify OS 2.0](https://img.shields.io/badge/Shopify-OS%202.0%20Ready-96bf48?logo=shopify&logoColor=white)](#-instalación-en-shopify)
[![Vanilla JS](https://img.shields.io/badge/JavaScript-100%25%20Vanilla-f7df1e?logo=javascript&logoColor=black)](#-principios-técnicos)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero-00b4d8)](#-principios-técnicos)
[![GPU Accelerated](https://img.shields.io/badge/Animations-60%20FPS%20GPU-7928ca)](#-principios-técnicos)

---

## 📂 Estructura del Repositorio

La carpeta y el repositorio están estructurados específicamente para escalar de forma ordenada conforme se agreguen nuevos elementos:

```
w-belm/
├── .gitignore                    # Reglas de exclusión de Git
├── README.md                     # Documentación general del repositorio
├── index.html                    # Showcase / Catálogo interactivo de elementos
├── elements/                     # Directorio central de elementos individuales
│   ├── bubb/                     # Elemento 1: Burbuja Asistente Flotante
│   │   ├── index.html            # Prototipo ejecutable directamente con doble clic
│   │   ├── style.css             # Estilos y animaciones aisladas (prefijo bb-)
│   │   ├── spike.png             # Asset gráfico del elemento
│   │   ├── bubb-widget.liquid    # Sección Shopify OS 2.0
│   │   └── README.md             # Especificación técnica detallada de Bubb
│   └── _template/                # Plantilla base para crear nuevos elementos
│       ├── index.html            # Boilerplate del prototipo
│       ├── style.css             # Boilerplate de estilos y variables
│       ├── element.liquid        # Boilerplate de sección Shopify con schema
│       └── README.md             # Checklist para desarrollo de nuevos elementos
├── shopify/                      # Distribución lista para copiar en temas Shopify
│   ├── sections/
│   │   └── bubb-widget.liquid    # Secciones para la carpeta /sections del tema
│   ├── assets/
│   │   └── spike.png             # Assets para la carpeta /assets del tema
│   └── README.md                 # Guía de instalación rápida en Shopify
└── docs/
    └── ARCHITECTURE.md           # Estándares de ingeniería y diseño
```

---

## 🧩 Catálogo de Elementos

### 1. [Bubb — Asistente Flotante & Chaos Panel](elements/bubb/)
- **Estado**: `Producción v1.0`
- **Prefijo de namespace**: `bb-`
- **Características**:
  - Burbuja translúcida con física de fluidos mediante gradientes radiales superpuestos y refracción óptica con `backdrop-filter`.
  - Modo alternable **Silueta Spike** con filtro SVG óptico sobre la transparencia del logo.
  - **Arrastre libre (Mouse y Táctil)** mediante Pointer Events API con umbral de 6px, sin interferir con clics ni micro-interacciones.
  - Contenedor externo de posición separado (`transform: translate3d`) del contenedor de animaciones, previniendo colisiones de transforms.
  - Confinamiento dinámico a la pantalla (*clamping*) considerando `safe-area-inset-*` y redimensionamiento móvil.
  - Persistencia de posición en `localStorage` con recuperación automática al cargar.
  - Control accesible por teclado: flechas mueven 10px (`Shift` = 40px), `Enter` / `Espacio` abren el panel.
  - Micro-interacciones: pulso elástico de gelatina, gesto curioso cada 9s, y giro de 720° con rotación tras pasar el cursor más de 2 veces en ráfaga.
  - Modal "Welcome to The Chaos" con apertura inteligente hacia el cuadrante con más espacio libre.
  - Variante de color invertida para **Modo Oscuro** (`is-dark-theme`).
  - Cumplimiento riguroso con `prefers-reduced-motion: reduce`.

### 2. [Plantilla Base (`_template`)](elements/_template/)
- Estructura preconfigurada para clonar y comenzar el desarrollo de cualquier nuevo elemento (`cb-`, `mc-`, etc.).

---

## ⚡ Cómo Probar en Local

1. Clona el repositorio o descarga la carpeta.
2. Abre cualquier archivo `index.html` con **doble clic**:
   - `index.html`: Abre el portal / catálogo de todos los elementos.
   - `elements/bubb/index.html`: Abre directamente el prototipo interactivo de Bubb con su barra de pruebas.
   - `elements/_template/index.html`: Abre la plantilla base para desarrollo de nuevos componentes.
3. No requiere Node.js, npm, bundlers ni servidores locales.

---

## 🛠️ Principios Técnicos Obligatorios

1. **Aislamiento de Namespace**: Toda clase, ID, keyframe y variable CSS debe llevar el prefijo del elemento (ej. `bb-`).
2. **Animaciones a 60 FPS**: Animar únicamente `transform` y `opacity` (y `border-radius` para deformaciones orgánicas). Jamás animar dimensiones ni posiciones de layout (`top`, `left`, `width`, `height`).
3. **Cero Dependencias**: 100% Vanilla JavaScript y CSS nativo.
4. **Pointer Events**: Uso de eventos de puntero unificados con `setPointerCapture` y `touch-action: none`.
5. **Accesibilidad**: Navegación por teclado completa, `:focus-visible`, sincronización de estados ARIA y respeto a `prefers-reduced-motion`.

---

## 🛍️ Instalación en Shopify

1. Copia los archivos dentro de `shopify/sections/` a la carpeta `sections/` de tu tema Shopify.
2. Copia los archivos dentro de `shopify/assets/` a la carpeta `assets/` de tu tema.
3. En `layout/theme.liquid`, agrega antes de `</body>`:
   ```liquid
   {% section 'bubb-widget' %}
   ```
4. O agrégalo como sección mediante el Theme Customizer de Shopify.

Consulta [shopify/README.md](shopify/README.md) y [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) para más detalles.

---

## 👤 Autor

- **whoisgiov2** ([github.com/whoisgiov2/w-belm](https://github.com/whoisgiov2/w-belm))
