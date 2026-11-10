# Shopify Theme Ready Distribution

Este directorio contiene los componentes listos para ser incorporados directamente en un tema de Shopify (Online Store 2.0).

---

## 📂 Estructura

```
shopify/
├── sections/
│   └── bubb-widget.liquid   <- Sección independiente con schema configurable
└── assets/
    └── spike.png            <- Logo por defecto para la silueta del widget
```

---

## ⚡ Guía Rápida de Instalación

1. **Copiar sección**:
   Copia el archivo `shopify/sections/bubb-widget.liquid` a la carpeta `sections/` de tu tema Shopify.

2. **Copiar asset**:
   Copia `shopify/assets/spike.png` a la carpeta `assets/` de tu tema.

3. **Renderizar en la tienda**:
   - **Opción A (Global en todas las páginas)**:
     Abre `layout/theme.liquid` e inserta la siguiente línea justo antes de la etiqueta de cierre `</body>`:
     ```liquid
     {% section 'bubb-widget' %}
     ```
   - **Opción B (Editor Visual de Temas)**:
     Ve a *Personalizar tema* en tu panel de Shopify, haz clic en *Agregar sección* y selecciona **Bubb Asistente Flotante**.

---

## ⚙️ Parámetros del Customizer (Schema)

- **Variante de color**: Alterna entre *Modo Claro (Original)* y *Modo Oscuro (Colores Invertidos)*.
- **Modo visual**: Alterna entre *Silueta Spike como burbuja* y *Burbuja esférica con logo interior*.
- **Logo personalizado**: Selector de imagen para reemplazar el logo por defecto.
- **Tamaño y posición**: Controles deslizantes para diámetro (`60px` a `120px`), márgenes derecho e inferior.
- **Textos y URLs**: Configura el título, mensaje de invitación, URL de registro (`/account/register`) y URL de login (`/account/login`).
