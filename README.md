# w-belm — Elementos y Micro-interacciones para Shopify

> Colección de componentes frontend interactivos (asistentes flotantes, banners, efectos hover, etc.) diseñados en **JavaScript Vanilla** y **CSS puro**, listos para reemplazar elementos por defecto en cualquier tienda **Shopify (Online Store 2.0)** sin romper el diseño existente.

---

## 📁 Estructura del Repositorio

La carpeta está organizada para que cada elemento cuente con su prototipo de prueba local y su archivo listo para instalar en Shopify:

```text
w-belm/
├── README.md                      # Guía general de integración en tiendas Shopify
├── .gitignore                     # Exclusiones de Git
├── index.html                     # Visualizador local de los elementos disponibles
│
├── elements/                      # Componentes interactivos
│   └── bubb/                      # Asistente flotante (Burbuja & Chaos Panel)
│       ├── index.html             # Prototipo local (doble clic para probar)
│       ├── style.css              # Estilos y micro-interacciones (prefijo bb-)
│       ├── bubb-widget.liquid     # Sección para Shopify OS 2.0
│       ├── spike.png              # Asset gráfico del logo / silueta
│       └── README.md              # Guía específica de integración para Bubb
│
└── shopify/                       # Archivos listos para copiar a tu tema de Shopify
    ├── sections/
    │   └── bubb-widget.liquid     # Secciones listas para /sections/
    ├── assets/
    │   └── spike.png              # Imágenes listas para /assets/
    └── README.md                  # Instrucciones rápidas de instalación en el tema
```

*(Conforme se agreguen nuevos elementos como banners u hovers, cada uno tendrá su propia carpeta en `elements/<nombre>/` con su prototipo y archivo Liquid para reemplazar la sección correspondiente).*

---

## 🛍️ Guía de Integración para Cualquier Tienda Shopify

Los elementos de este repositorio están pensados para **reemplazar o enriquecer componentes existentes** dentro de tu tienda (por ejemplo, reemplazar el botón flotante de chat/soporte por Bubb, o reemplazar un banner estático por uno interactivo).

### Paso 1: Subir los archivos a tu tema de Shopify

1. En tu panel de administración de Shopify, ve a **Tienda online > Temas**.
2. En tu tema actual (ej. *Dawn, Prestige, Impulse, Horizon, Sense*), haz clic en los tres puntos `···` y selecciona **Editar código**.
3. **Secciones**: En la carpeta `sections/`, haz clic en *Agregar una nueva sección*, nómbrala `bubb-widget.liquid` y pega el contenido del archivo `shopify/sections/bubb-widget.liquid`.
4. **Assets**: En la carpeta `assets/`, haz clic en *Agregar un nuevo recurso* y sube `shopify/assets/spike.png` (o el logo transparente de tu marca).

---

### Paso 2: Cómo reemplazar o insertar el elemento en la página

Tienes dos formas de activar el elemento según cómo quieras que funcione en la tienda:

#### Opción A: Desde el Editor Visual de Shopify (Recomendado)
*Ideal para reemplazar secciones de página (banners, bloques interactivos) sin tocar código:*

1. Ve a **Tienda online > Temas > Personalizar**.
2. Si vas a **reemplazar un elemento existente** (por ejemplo, un banner o formulario anterior), haz clic sobre él en el menú izquierdo y selecciona **Ocultar** (ícono de ojo) o **Eliminar sección**.
3. Haz clic en **Agregar sección** (en la parte inferior del menú de la página o en la barra lateral).
4. Busca y selecciona **Bubb Asistente Flotante** (o el elemento que desees).
5. Guarda los cambios.

#### Opción B: Integración Global en `theme.liquid`
*Ideal para elementos flotantes que deben acompañar al cliente en toda la navegación (como Bubb):*

1. En **Editar código**, abre el archivo `layout/theme.liquid`.
2. Ve al final del archivo y busca la etiqueta de cierre `</body>`.
3. Justo **antes** de `</body>`, agrega la siguiente línea:
   ```liquid
   {% section 'bubb-widget' %}
   ```
4. Guarda el archivo. El widget aparecerá automáticamente en todas las páginas de la tienda (Home, Colecciones, Productos, Carrito, etc.).

---

### Paso 3: Adaptar el diseño a la identidad de tu tienda

Cada elemento está construido para sincronizarse fácilmente con los colores, fuentes y estilos de cualquier tema:

1. **Colores de la marca**:
   - En el Editor de Temas de Shopify, selecciona la sección agregada.
   - Modifica el **Color de acento** para que coincida con el color principal de tu marca (por defecto `#4f46e5`).
   - Puedes alternar entre **Modo Claro** y **Modo Oscuro (Colores Invertidos)** para tiendas con fondos oscuros.

2. **Tipografía del tema**:
   - El elemento hereda automáticamente la fuente tipográfica definida en tu tema de Shopify (`font-family: inherit;`), por lo que los textos se verán exactamente iguales al resto de tu tienda.

3. **URLs y Redirecciones**:
   - En el panel de configuración puedes definir a dónde llevan los botones. Por defecto:
     - Botón *JOIN THE CHAOS*: redirige a la página de registro de clientes (`/account/register`).
     - Enlace *¿yA tIEnES cuEnTa?*: redirige a la página de login (`/account/login`).

4. **Modo Silueta vs Esférico**:
   - Puedes elegir si quieres que la burbuja tome la silueta de tu logo (`is-spike-mode`) o si prefieres una burbuja esférica con el logo dentro.

---

### Paso 4: Pruebas y Verificación Responsive

- **Dispositivos móviles (iPhone / Android)**: El elemento respeta automáticamente las zonas seguras (`env(safe-area-inset-bottom)`), evitando que se sobreponga con la barra de navegación del celular o botones de compra fijos.
- **Arrastre libre**: El cliente puede arrastrar la burbuja a cualquier punto de la pantalla para apartarla si le estorba. La tienda recordará su posición en ese dispositivo.
- **Accesibilidad**: Si un cliente tiene activada la reducción de movimiento en su sistema (*prefers-reduced-motion*), las animaciones intensas se apagan automáticamente y se reemplazan por transiciones suaves.

---

## 💻 Cómo Probar los Prototipos en Local

No necesitas instalar Node.js, librerías ni configurar ningún servidor.

1. Abre el archivo **[index.html](file:///c:/Users/crm/Downloads/Bubb/index.html)** en la raíz con doble clic para ver el catálogo de elementos disponibles.
2. O abre directamente **[elements/bubb/index.html](file:///c:/Users/crm/Downloads/Bubb/elements/bubb/index.html)** con doble clic para interactuar con la burbuja, moverla por la pantalla, probar la explosión y usar su barra de pruebas superior.
