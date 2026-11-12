# Gift Card — Tarjeta de Descuento de Bienvenida al Caos (`gift_card.liquid`)

> Tarjeta digital y plantilla de correo electrónico para clientes con formato **minimalista**, fondo integral con la textura artística de **`fondoini.jpg`**, estética **Rojo Caos (`#780606`)** y tipografías **Luckiest Guy** & **Carter One**.

---

## 🎨 Características de Diseño (Diferenciación con el Popup de Spike)

A diferencia del desplegable de Spike (que utiliza un modal con fondo blanco y avatar circular sobresaliente tipo chat), esta tarjeta está concebida como un **voucher digital minimalista y compatible con clientes de correo**:

- **Fondo Integral con `fondoini.jpg`**:
  Toda la tarjeta está envuelta en la textura artística de la marca con una capa de gradiente oscuro carmesí que garantiza contraste y legibilidad perfecta.
- **Estructura Híbrida para Correo (Email-First)**:
  Maquetada con tablas HTML, estilos inlined y marcado condicional VML para Microsoft Outlook. Compatible con Gmail, Apple Mail, Outlook, Yahoo Mail y clientes móviles.
- **Tipografía de Alto Impacto**:
  - `Luckiest Guy`: Título principal (*"Te damos la bienvenida al caos."*), destacado (*"10% de descuento"*) y botón de acción (*"APLICAR DESCUENTO"*).
  - `Carter One`: Insignia (*"Oferta especial"*), ubicación (*"en Página de inicio"*) y código (*"WELCOME10"*).
- **Enlace de Descuento Automático de Shopify**:
  El botón `[Aplicar descuento]` redirige directamente a `/discount/WELCOME10?redirect=/`, aplicando automáticamente el descuento en la sesión del cliente al ingresar a la tienda.
- **Caja de Cupón Minimalista**:
  Ticket pill con código de descuento claro, seleccionable en correos y con copiado en un clic en navegador web.

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
