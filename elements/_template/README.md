# Plantilla Base para Nuevos Elementos (`_template`)

Utiliza esta carpeta como base cada vez que vayas a construir un nuevo elemento, widget o micro-interacción para la biblioteca `w-belm`.

---

## 📋 Pasos para Crear un Nuevo Elemento

1. **Duplica esta carpeta**:
   Copia `elements/_template/` a una nueva carpeta con el nombre de tu elemento dentro de `elements/` (por ejemplo: `elements/chaos-banner/` o `elements/magnetic-card/`).

2. **Asigna un prefijo único de 2-4 letras**:
   - Ejemplo: `cb-` para Chaos Banner, `mc-` para Magnetic Card (Bubb utiliza `bb-`).
   - Aplica este prefijo a todas las clases CSS, IDs, animaciones `@keyframes` y variables CSS.
   - Esto garantiza aislamiento total y cero conflictos con temas de Shopify.

3. **Desarrolla el prototipo (`index.html` y `style.css`)**:
   - Vanilla puro (sin React, sin Tailwind, sin CDN externos).
   - Debe funcionar abriendo `index.html` con doble clic desde Windows/macOS.
   - Mantén animaciones aceleradas por hardware (`transform` y `opacity`).
   - Soporte para `prefers-reduced-motion` y navegación por teclado.

4. **Empaqueta para Shopify (`element.liquid`)**:
   - Agrega el bloque `<style>` y `<script>` encapsulados por `section.id`.
   - Define el schema en `{% schema %}` para permitir personalización en el editor de Shopify.
   - Crea un duplicado en `shopify/sections/<tu-elemento>.liquid`.

5. **Registra el nuevo elemento en el Showcase**:
   - Agrega la tarjeta correspondiente en el `index.html` raíz de `w-belm`.
   - Actualiza la lista en el `README.md` principal.
