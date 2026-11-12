# Gift Card — Tarjeta de Descuento de Bienvenida al Caos (`gift_card.liquid`)

> Tarjeta de regalo y cupón digital de bienvenida para clientes, con el diseño **Rojo Caos (#780606)**, banner superior grunge (`fondoini.jpg`), insignia de marca (`spike.png`) y tipografías **Luckiest Guy** & **Carter One**.

---

## 🎨 Características

- **Diseño estilo Voucher / Ticket**: Cabecera con banner y gradiente oscuro, insignia circular flotante de Spike, contenedor de alta legibilidad y borde con halo carmesí.
- **Tipografías Google Fonts**:
  - `Luckiest Guy`: Título principal (*"Te damos la bienvenida al caos."*), destacado (*"10% de descuento"*) y botón de acción principal (*"APLICAR DESCUENTO"*).
  - `Carter One`: Insignia (*"Oferta especial"*), etiqueta y valor del cupón (*"WELCOME10"*).
- **Enlace de Descuento Automático de Shopify**:
  El botón `[Aplicar descuento]` redirige a `/discount/WELCOME10?redirect=/`, aplicando automáticamente el descuento en la sesión del cliente al momento de ingresar a la tienda.
- **Botón de Copiado Rápido**:
  Copia el código al portapapeles con un solo clic con feedback visual interactivo.
- **Soporte de Impresión**:
  Optimizado con reglas `@media print` para que el cliente pueda imprimir su tarjeta limpia en papel o PDF.
- **100% Responsive**:
  Se adapta fluidamente a pantallas móviles, tablets y monitores de escritorio.

---

## 🛍️ Métodos de Integración en Shopify

Este archivo se puede utilizar de dos maneras según tus necesidades:

### Opción 1: Plantilla de Tarjeta de Regalo en tu Tema (`templates/gift_card.liquid`)

Cuando un cliente recibe una tarjeta de regalo emitida por Shopify o accede a su enlace web de tarjeta de regalo (`gift_card.url`), Shopify renderiza esta plantilla.

1. En tu panel de administración de Shopify, ve a **Tienda online > Temas**.
2. En tu tema actual, haz clic en `···` > **Editar código**.
3. En la barra lateral izquierda, busca la carpeta **`templates/`**.
4. Si ya existe `gift_card.liquid`, haz clic sobre él para abrirlo (o haz clic en *Agregar una nueva plantilla*, selecciona `gift_card` y nómbrala `gift_card.liquid`).
5. Reemplaza todo el contenido con el archivo [shopify/templates/gift_card.liquid](file:///c:/Users/crm/Downloads/Bubb/shopify/templates/gift_card.liquid).
6. En la carpeta **`assets/`**, asegúrate de tener subidos:
   - `fondoini.jpg`
   - `spike.png`
7. Haz clic en **Guardar**.

---

### Opción 2: Plantilla de Notificación por Correo Electrónico (Email)

Para que el cliente reciba este diseño directamente en su bandeja de entrada de correo:

1. En tu panel de administración de Shopify, ve a **Configuración > Notificaciones > Notificaciones de clientes**.
2. Selecciona la notificación que deseas personalizar (por ejemplo: **Tarjeta de regalo creada** o **Contacto con el cliente**).
3. Haz clic en **Editar código** o **Personalizar**.
4. Pega el código de `gift_card.liquid` dentro del cuerpo de la notificación.
5. Haz clic en **Enviar correo de prueba** para verificar que llegue correctamente a tu buzón.

---

## 💻 Prototipo Local de Pruebas

Para ver el diseño y probar la tarjeta sin necesidad de subirlo a Shopify:
1. Haz doble clic en el archivo local **[elements/gift-card/index.html](file:///c:/Users/crm/Downloads/Bubb/elements/gift-card/index.html)**.
2. Utiliza la barra de herramientas superior para conmutar entre vista **Desktop**, vista **Móvil** o **Simulador de Correo**.
