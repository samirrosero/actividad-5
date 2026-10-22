# Nuestro Equipo – Tarjetas de perfil

Ejercicio práctico de maquetación de tarjetas de perfil usando **HTML**, **CSS**, la propiedad **`clip-path`**, iconos de **Font Awesome** (CDN) y la metodología **BEM**.

El diseño toma como base el ejercicio *Practical Time* (dos tarjetas con cabecera y pie recortados), pero con una propuesta propia: otra paleta de colores, tres tarjetas con formas distintas y avatares recortados con `clip-path`.

Basado en el repositorio: [uniajc-gperezm/responsive-design-media-query](https://github.com/uniajc-gperezm/responsive-design-media-query)

🔗 **Demo en GitHub Pages:** [https://samirrosero.github.io/actividad-5/](https://samirrosero.github.io/actividad-5/)

📁 **Repositorio:** [https://github.com/samirrosero/actividad-5](https://github.com/samirrosero/actividad-5)

## Estructura

```
├── css/
│   └── styles.css
├── index.html
└── README.md
```

## Tecnologías

- HTML5 semántico (`main`, `section`, `article`, `header`, `footer`)
- CSS3 (Grid, Flexbox, variables CSS, degradados, `clip-path`, media queries)
- [Font Awesome 7.3.1](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.3.1/css/all.min.css) vía CDN
- Fuente de Google: *Poppins*

## Diseño

| Tarjeta | Color | Cabecera | Avatar | Botones | Pie |
|---------|-------|----------|--------|---------|-----|
| `tarjeta--hexagono` | Turquesa | Punta en V | Hexágono | Hexágonos | Muesca en V |
| `tarjeta--zigzag` | Coral | Borde dentado | Círculo | Rombos | Borde dentado |
| `tarjeta--octagono` | Ámbar | Corte diagonal | Octágono | Octágonos | Esquinas cortadas |

Al pasar el mouse, la tarjeta se eleva y los botones se rellenan con el color de acento.

## Uso de `clip-path`

Las formas se hicieron con polígonos (`polygon`) y círculos (`circle`). Se pueden ver y ajustar de forma visual en [Clippy](https://clippy.f8.edu.vn/).

| Forma | `clip-path` |
|-------|-------------|
| Cabecera en V | `polygon(0 0, 100% 0, 100% 70%, 50% 100%, 0 70%)` |
| Cabecera diagonal | `polygon(0 0, 100% 0, 100% 55%, 0 100%)` |
| Hexágono | `polygon(50% 0, 100% 25%, 100% 75%, 50% 100%, 0 75%, 0 25%)` |
| Octágono | `polygon(30% 0, 70% 0, 100% 30%, 100% 70%, 70% 100%, 30% 100%, 0 70%, 0 30%)` |
| Rombo | `polygon(50% 0, 100% 50%, 50% 100%, 0 50%)` |
| Círculo | `circle(50%)` |
| Zigzag | polígono con puntos alternados cada 5% del ancho |

Cada modificador guarda la forma del avatar y de los botones en variables CSS (`--forma-avatar`, `--forma-accion`), junto con sus colores (`--acento`, `--acento-oscuro`). Así el bloque `.tarjeta` usa siempre las mismas reglas y solo cambian los valores.

## Metodología BEM

**BEM** (*Bloque, Elemento, Modificador*) es una convención para nombrar clases CSS que hace el código más legible, reutilizable y evita conflictos de especificidad.

- **Bloque**: componente independiente → `.tarjeta`
- **Elemento**: parte del bloque, se une con `__` → `.tarjeta__cabecera`, `.tarjeta__avatar`, `.tarjeta__nombre`
- **Modificador**: variante del bloque, se une con `--` → `.tarjeta--hexagono`, `.tarjeta--zigzag`, `.tarjeta--octagono`

Clases usadas en el proyecto:

```
equipo
├── equipo__encabezado
│   ├── equipo__titulo
│   └── equipo__subtitulo
└── equipo__tablero

tarjeta  (tarjeta--hexagono | tarjeta--zigzag | tarjeta--octagono)
├── tarjeta__cabecera
│   └── tarjeta__marco
│       └── tarjeta__avatar
├── tarjeta__cuerpo
│   ├── tarjeta__nombre
│   ├── tarjeta__rol
│   ├── tarjeta__separador
│   ├── tarjeta__texto
│   └── tarjeta__acciones
│       └── tarjeta__accion
└── tarjeta__pie
    └── tarjeta__redes
        └── tarjeta__enlace-red
```

## Diseño adaptable

- Las tarjetas se acomodan con CSS Grid (`repeat(auto-fit, minmax(...))`): tres por fila en pantallas grandes, dos en medianas y una en celulares.
- Las media queries ajustan el tamaño del título, los espacios y el ancho de las tarjetas en pantallas pequeñas.

## Cómo verlo en local

```bash
git clone https://github.com/samirrosero/actividad-5.git
cd actividad-5
```

Luego abrir `index.html` en el navegador.

## Publicación en GitHub Pages

1. En el repositorio, ir a **Settings → Pages**.
2. En **Source** elegir *Deploy from a branch*, rama `main` y carpeta `/ (root)`.
3. Guardar. La página queda publicada en [https://samirrosero.github.io/actividad-5/](https://samirrosero.github.io/actividad-5/).

## Autor

**Samir Rosero Armero** – [@samirrosero](https://github.com/samirrosero)
