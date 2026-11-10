# Archivos de Shopify (Distribución directa)

Esta carpeta contiene los archivos listos para copiar y pegar directamente dentro de las carpetas de tu tema de Shopify.

---

## 📁 Archivos incluidos

```text
shopify/
├── sections/
│   └── bubb-widget.liquid   <- Copiar a la carpeta /sections/ de tu tema
└── assets/
    └── spike.png            <- Copiar a la carpeta /assets/ de tu tema
```

---

## ⚡ Instalación en 2 minutos

1. En tu panel de Shopify, ve a **Tienda online > Temas > Editar código**.
2. Copia `sections/bubb-widget.liquid` a la carpeta `sections/` de tu tema.
3. Sube `assets/spike.png` a la carpeta `assets/` de tu tema.
4. Abre `layout/theme.liquid` y agrega antes de `</body>`:
   ```liquid
   {% section 'bubb-widget' %}
   ```
5. ¡Listo! Abre el personalizador visual del tema para ajustar colores, tamaño y textos.
