# Gift Card — Tarjeta de Descuento de Bienvenida al Caos (`gift_card.liquid`)

> Tarjeta digital y plantilla de correo electrónico para clientes con formato **minimalista**, fondo integral con la textura artística de **`fondoini.jpg`**, estética **Rojo Caos (`#780606`)** y tipografías **Luckiest Guy** & **Carter One**.

---

## 🎨 Diseño "Chaos Ticket" (póster editorial / zine)

Lenguaje visual propio, distinto al desplegable de Spike (sin esquinas redondeadas, sin pastillas, sin cajas punteadas ni avatar circular):

- **Fondo integral `fondoini.jpg`** con velo oscuro carmesí.
- **Cinta superior** roja con Spike, "WELCOME TO THE CHAOS" y nº de ticket.
- **"10%" gigante** (Luckiest Guy) con sombra dura desplazada en `#780606`, junto a "DE DESCUENTO / en Página de inicio".
- **Título tipo nota de rescate**: cada palabra de "Te damos la bienvenida al caos." en un bloque de color distinto.
- **Código en fichas**: cada carácter de `WELCOME10` en su propio bloque alternando blanco/rojo (se genera con un bucle Liquid sobre el código).
- **CTA en barra completa** de borde a borde: "APLICAR DESCUENTO" + bloque negro con flecha. Enlaza a `/discount/WELCOME10?redirect=/`.
- **Pie con código de barras decorativo** hecho con celdas de tabla (seguro para correo).
- **Email-first**: tablas, estilos inline, VML para Outlook, preheader oculto y fuentes de respaldo (`Impact`, `Trebuchet MS`).

---

## 🛍️ Cómo Instalarlo en Shopify

### Opción 1: Notificación de Correo Electrónico (Recomendada)
Para que los clientes reciban esta tarjeta al registrarse o al emitirles un descuento de bienvenida:
1. En tu panel de Shopify, ve a **Configuración > Notificaciones > Notificaciones de clientes**.
2. Selecciona la notificación correspondiente (por ejemplo: **Tarjeta de regalo creada** o **Contacto con el cliente**).
3. Haz clic en **Editar código**.
4. Pega el contenido de [shopify/templates/gift_card.liquid](file:///c:/Users/crm/Downloads/Bubb/shopify/templates/gift_card.liquid).
5. Envía un correo de prueba desde Shopify para validar la recepción en tu buzón.

### Opción 2: Plantilla de Tienda Online (`templates/gift_card.liquid`)
Cuando un cliente hace clic en el enlace web para ver su tarjeta de regalo en la tienda:
1. Ve a **Tienda online > Temas > Editar código**.
2. En la carpeta **`templates/`**, reemplaza `gift_card.liquid` con el archivo [shopify/templates/gift_card.liquid](file:///c:/Users/crm/Downloads/Bubb/shopify/templates/gift_card.liquid).
3. Asegúrate de tener subidos en la carpeta **`assets/`**:
   - `fondoini.jpg`
   - `spike.png`

---

## 💻 Prototipo Local
Abre con doble clic el archivo **[elements/gift-card/index.html](file:///c:/Users/crm/Downloads/Bubb/elements/gift-card/index.html)** para probar la vista en Desktop, Móvil o en el Simulador de Correo Electrónico.
