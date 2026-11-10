# Bubb — Asistente Flotante & Panel "Welcome to The Chaos"

> Elemento interactivo de alta fidelidad para tiendas Shopify y aplicaciones web modernas. Simula una burbuja de jabón translúcida con física de fluidos, silueta óptica SVG de la mascota Spike, arrastre libre con Pointer Events, memoria de posición, panel modal y soporte para temas claros y oscuros.

---

## 🚀 Características Principales

- **Física de fluidos en CSS puro**: Radial gradients superpuestos, refracción óptica con `backdrop-filter`, flotación senoidal, bamboleo y deformación elástica de `border-radius`.
- **Modo Silueta Spike**: Filtros ópticos SVG personalizados (`#bb-spike-soap-filter` y `#bb-spike-soap-filter-dark`) que proyectan la película jabonosa sobre la silueta transparente del logo.
- **Arrastre libre (Mouse y Táctil)**:
  - Implementado con **Pointer Events** (`pointerdown`, `pointermove`, `pointerup`, `pointercancel`, `setPointerCapture`).
  - Separación estricta entre posición (`transform: translate3d`) en el contenedor `.bb-bubble-wrap` y animaciones en `.bb-bubble`.
  - Umbral de 6px: movimientos menores activan la explosión/clic; mayores a 6px activan el arrastre.
  - Pausa de animaciones (`cursor: grabbing`) durante el arrastre.
  - Confinamiento a la pantalla (*clamping*) considerando `safe-area-inset-*` y redimensionamiento de ventana / teclado móvil (`visualViewport`).
  - Persistencia en `localStorage` con clave `bb_bubble_pos_v1` protegida en `try/catch`.
- **Control por teclado accesible**: Las teclas de flecha mueven la burbuja `10px` (`Shift + Flecha` = `40px`). `Enter` y `Espacio` abren el panel.
- **Micro-interacciones reactivas**:
  - Pulso elástico de gelatina al pasar el cursor o soltar el foco.
  - Gesto curioso automático cada ~9 segundos.
  - Giro de 720° con rotación al pasar el mouse más de 2 veces en ráfaga.
  - Destello perimetral continuo cada 5 segundos.
- **Transiciones y Panel modal**:
  - Explosión con anillo de choque y 12 gotitas disparadas en 360°.
  - Apertura inteligente: el panel detecta el cuadrante con mayor espacio en pantalla para expandirse.
  - Cierre con botón ×, tecla `Escape`, clic exterior o tras interactuar.
  - Regeneración inversa (implosión) si se cierra sin enviar.
- **Modo Oscuro Invertido**: Compatible automáticamente con `[data-theme="dark"]`, `.dark` o `.is-dark-theme`.
- **Accesibilidad y Rendimiento**: Respeto estricto a `prefers-reduced-motion: reduce` (fades suaves sin gotitas ni giros) y navegación por tabulador con `:focus-visible`.

---

## 📁 Archivos del Elemento

| Archivo | Descripción |
|---|---|
| `index.html` | Prototipo individual ejecutable directamente con doble clic (sin servidores ni dependencias). Incluye barra de pruebas superior. |
| `style.css` | Hoja de estilos completa con prefijo de aislamiento `bb-` y delimitadores para integración en Shopify. |
| `bubb-widget.liquid` | Sección modular para Shopify OS 2.0 lista para instalar en `/sections/`. |
| `spike.png` | Asset gráfico del logo / silueta. |

---

## 🎨 Variables CSS Configurables

En `:root` (o en `.bb-root-{{ section.id }}` dentro de Shopify):

```css
:root {
  --bb-size: 84px;           /* Diámetro de la burbuja */
  --bb-accent: #4f46e5;      /* Color de acento de la marca */
  --bb-right: 24px;          /* Separación del margen derecho */
  --bb-bottom: 24px;         /* Separación del margen inferior */
  --bb-float-time: 4s;       /* Duración del ciclo de flotación senoidal */
  --bb-squash-scale: 1.06;   /* Intensidad del rebote squash & stretch */
}
```

---

## 🛍️ Instalación en Shopify

1. Copia `bubb-widget.liquid` a la carpeta `sections/` de tu tema Shopify.
2. Sube `spike.png` a la carpeta `assets/` de tu tema.
3. Agrega la sección en `layout/theme.liquid` antes de `</body>`:
   ```liquid
   {% section 'bubb-widget' %}
   ```
   *O agrégala directamente como sección global en el Editor de Temas de Shopify.*
