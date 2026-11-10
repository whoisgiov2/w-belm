# Bubb — Asistente Flotante ("Welcome to The Chaos")

> Widget interactivo diseñado para reemplazar o complementar botones flotantes de contacto, chats o popups convencionales en tiendas Shopify.

---

## 🎯 ¿Qué elemento reemplaza en tu tienda?

En la mayoría de tiendas Shopify se suelen usar apps pesadas para botones de chat, WhatsApp flotante o formularios de suscripción que ralentizan la carga y chocan visualmente con la tienda.

**Bubb reemplaza esos botones tradicionales con:**
- Una micro-interacción de alta gama (burbuja de jabón con física de fluidos y silueta óptica del logo).
- Arrastre libre táctil y mouse con memoria de posición en el navegador.
- Un panel modal rápido ("Welcome to The Chaos") con botón directo de registro (`JOIN THE CHAOS`) y enlace a login (`¿yA tIEnES cuEnTa?`).
- Cero dependencias: no afecta la velocidad de carga (Lighthouse score intacto).

---

## 🛠️ Paso a Paso para Integrarlo a tu Tema de Shopify

### 1. Copiar los archivos al tema
1. Ve a **Tienda online > Temas > Editar código**.
2. En la carpeta `sections/`, crea el archivo `bubb-widget.liquid` y pega el código de este elemento.
3. En la carpeta `assets/`, sube `spike.png` (o el logo transparente de tu tienda).

### 2. Mostrarlo en toda la tienda
Para que la burbuja aparezca flotando en todas las páginas de tu tienda:
1. Abre el archivo `layout/theme.liquid`.
2. Busca la línea `</body>` casi al final del archivo.
3. Justo arriba de `</body>`, agrega:
   ```liquid
   {% section 'bubb-widget' %}
   ```
4. Guarda los cambios.

### 3. Personalizarlo desde el Editor de Shopify
Ve a **Personalizar tema** en el panel de Shopify. Podrás configurar:
- **Modo visual**: Silueta de Spike interactiva o Burbuja esférica clásica.
- **Variante de color**: 
  - **Crimson Caos (#780606)**: Diseñada con matices rojo carmesí / vino profundo para integrarse con la tienda.
  - **Modo Claro (Original)**: Burbuja translúcida iridiscente con acento índigo.
  - **Modo Oscuro (Invertido)**: Variante luminosa de alto contraste para temas negros.
- **Logo personalizado**: Sube cualquier logo transparente en formato PNG o SVG.
- **Tamaño y posición**: Ajusta el diámetro de la burbuja y los márgenes respecto a la esquina inferior derecha.
- **URLs de destino**: Cambia los enlaces de registro y login si usas páginas personalizadas.

---

## 🧪 Cómo probarlo en tu computadora

Abre el archivo `index.html` de esta carpeta con **doble clic**.
Podrás:
- Arrastrar la burbuja libremente con el mouse.
- Probar el teclado (las flechas mueven la burbuja, `Enter` la abre).
- Usar la barra de pruebas superior para alternar entre el **Tema Claro**, **Tema Oscuro** y la nueva variante **Crimson (#780606)**, forzar la explosión o alternar entre el modo silueta y esfera.
