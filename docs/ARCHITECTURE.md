# Arquitectura y Guía de Contribución — w-belm

> Estándares de ingeniería y diseño para el desarrollo de componentes, widgets y micro-interacciones dentro del ecosistema `w-belm`.

---

## 🏛️ Principios de Diseño

1. **Aislamiento Total de Espacios de Nombres (Prefix Scoping)**:
   - Todo elemento debe tener un prefijo único de 2 a 4 caracteres (ejemplo: `bb-` para Bubb, `cb-` para Chaos Banner, `mc-` para Magnetic Card).
   - El prefijo aplica a:
     - Clases CSS (`.bb-bubble`, `.bb-panel`).
     - Identificadores DOM (`#bb-root`, `#bb-panel`).
     - Animaciones `@keyframes` (`@keyframes bb-rise`).
     - Variables CSS personalizadas (`--bb-accent`, `--bb-size`).
   - Esto evita colisiones con el CSS global de Shopify o librerías de terceros instaladas por clientes.

2. **Rendimiento GPU a 60 FPS (Hardware Acceleration)**:
   - **Regla estricta**: Animar únicamente `transform` y `opacity` (y `border-radius` para deformaciones orgánicas).
   - **Prohibido**: Nunca animar `top`, `left`, `bottom`, `right`, `width`, `height`, `margin` ni `padding`, ya que provocan *reflows* y *repaints* costosos que degradan la experiencia móvil.
   - En elementos móviles o arrastrables, separar el transform de posición del transform de animación mediante contenedores anidados (como `.bb-bubble-wrap` vs `.bb-bubble`).

3. **Cero Dependencias (Pure Vanilla)**:
   - Prohibido el uso de React, Vue, jQuery, Tailwind runtime o CDNs externos.
   - Todo debe funcionar sin proceso de compilación (*build-less*), abriendo directamente `index.html` con doble clic.

4. **Eventos de Puntero Unificados (Pointer Events API)**:
   - Emplear `pointerdown`, `pointermove`, `pointerup`, `pointercancel` y `setPointerCapture`.
   - Establecer `touch-action: none` en superficies arrastrables para evitar interferencias con el scroll nativo.
   - Usar un umbral de activación (ejemplo: 6px) para distinguir con precisión entre clics táctiles e intenciones de arrastre.

5. **Accesibilidad Universal (A11y)**:
   - Todos los elementos interactivos deben ser operables mediante teclado (`Tab`, `Enter`, `Espacio`, `Escape` y `Flechas`).
   - Atributos semánticos `aria-label`, `aria-expanded` y `aria-controls` sincronizados en cada cambio de estado.
   - Indicadores visuales claros `:focus-visible`.
   - Compatibilidad completa con `prefers-reduced-motion: reduce`: suprimir oscilaciones continuas, sacudidas y explosiones, reemplazándolas con transiciones suaves de opacidad.

6. **Soporte Nativo de Temas (Claro / Oscuro)**:
   - Todo elemento debe incorporar una variante de contraste invertido.
   - Detección automática mediante selectores globales: `[data-theme="dark"]`, `.dark`, o clase propia `.is-dark-theme`.

---

## 📁 Estructura del Repositorio

```
w-belm/
├── .gitignore                    # Reglas de exclusión de Git
├── README.md                     # Documentación principal de la colección
├── index.html                    # Showcase / Hub local interactivo
├── elements/                     # Directorio de elementos individuales
│   ├── bubb/                     # Asistente flotante (Burbuja & Chaos Panel)
│   │   ├── index.html            # Prototipo ejecutable con doble clic
│   │   ├── style.css             # Estilos independientes (prefijo bb-)
│   │   ├── bubb-widget.liquid    # Sección Shopify OS 2.0
│   │   ├── spike.png             # Asset gráfico
│   │   └── README.md             # Guía técnica de Bubb
│   └── _template/                # Plantilla base estandarizada
│       ├── index.html
│       ├── style.css
│       ├── element.liquid
│       └── README.md
├── shopify/                      # Distribución lista para copiar en temas Shopify
│   ├── sections/                 # Secciones para /sections/
│   │   └── bubb-widget.liquid
│   ├── assets/                   # Assets para /assets/
│   │   └── spike.png
│   └── README.md                 # Guía de instalación en Shopify
└── docs/
    └── ARCHITECTURE.md           # Estándares técnicos y de desarrollo
```

---

## 🛠️ Ciclo de Vida en Shopify OS 2.0

Cada sección `.liquid` debe implementar:
- Configuración editable mediante `{% schema %}`.
- Manejo del evento `shopify:section:load` para reinicializar scripts cuando el usuario edita valores en el Theme Customizer de Shopify.
- AbortController y limpieza de `setInterval` / listeners para prevenir fugas de memoria al recargar la sección.
