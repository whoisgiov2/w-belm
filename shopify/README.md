# Archivos de Shopify (Distribución directa)

Esta carpeta contiene los archivos listos para copiar y pegar directamente dentro de las carpetas de tu tema de Shopify (Online Store 2.0).

---

## 📁 Archivos incluidos

```text
shopify/
├── sections/
│   └── bubb-widget.liquid   <- Copiar a la carpeta /sections/ de tu tema
├── templates/
│   └── gift_card.liquid     <- Copiar a la carpeta /templates/ de tu tema
└── assets/
    ├── spike.png            <- Copiar a la carpeta /assets/ de tu tema
    └── fondoini.jpg         <- Copiar a la carpeta /assets/ de tu tema
```

---

## ⚡ Instalación Rápida por Elemento

### 1. Elemento Bubb (Asistente Flotante)
1. Copia `sections/bubb-widget.liquid` a la carpeta `sections/` de tu tema.
2. Sube `assets/spike.png` y `assets/fondoini.jpg` a la carpeta `assets/`.
3. Abre `layout/theme.liquid` y agrega antes de `</body>`:
   ```liquid
   {% section 'bubb-widget' %}
   ```
4. Guarda el archivo y personaliza colores y enlaces en el editor visual de temas.

### 2. Elemento Gift Card (`gift_card.liquid`)
1. Copia `templates/gift_card.liquid` a la carpeta `templates/` de tu tema (o úsalo en **Configuración > Notificaciones > Tarjeta de regalo creada**).
2. Asegúrate de tener subidos `assets/spike.png` y `assets/fondoini.jpg`.
3. El botón aplica automáticamente el cupón de bienvenida mediante `/discount/WELCOME10?redirect=/`.
