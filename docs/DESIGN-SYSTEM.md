# KARBÓN — Design System & Theme Guide

Este documento define la identidad visual y de voz del sitio de KARBÓN.
Úsalo como referencia cada vez que edites el código o le pidas cambios a una IA:
**adjunta este archivo junto con `index.html`** para que los cambios respeten el tema.

---

## 1. Esencia de la marca

| | |
|---|---|
| **Qué es** | Carnicería premium al carbón en San Salvador |
| **Sensación** | Steakhouse de noche: carbón encendido, madera, acero, oro viejo |
| **NO es** | Corporativo, plástico, genérico, "startup tech" |
| **Referencias** | HG Walter (drama + elegancia), Turner & George (honestidad artesanal) — pero KARBÓN es oscuro, salvadoreño y al carbón |

---

## 2. Cómo evitar que se vea "generado por IA"

Esta es la lista de las cosas que delatan un sitio hecho por IA — y cómo corregirlas.
**Revisa esta lista después de cada cambio.**

| Delator de IA | Corrección |
|---|---|
| Ilustraciones/clip-art de productos | **Fotos reales** de tus cortes (ver sección 7). Es el cambio nº 1 |
| Emojis usados como íconos (🏬 ♦ ▣ ⏱) | Íconos SVG de una sola línea, o texto simple |
| Datos inventados ("1,200+ clientes", "Est. 2026") | Datos reales o quitar la cifra. Nunca inventar números |
| Teléfono/dirección placeholder (7777-0000) | Datos reales del negocio |
| Copy genérico ("cortes premium seleccionados a mano") | Especificidad: nombre del corte, origen, cómo se madura, quién lo corta |
| Todas las secciones con el mismo ritmo (título + grid de tarjetas) | Variar: una sección de foto grande, una cita, una lista simple |
| Superlativos vacíos ("el mejor", "increíble", "experiencia única") | Hechos verificables ("maduramos 21 días", "res criolla de Chalatenango") |
| Perfección simétrica en todo | Detalles humanos: una foto torcida, una nota manuscrita, firma del carnicero |
| Gradientes y brillos en cada elemento | Reservar el brillo/fuego para el hero. El resto, sobrio |

**Regla de oro:** cada texto del sitio debe poder decirlo un carnicero real en voz alta sin sonar raro.

---

## 3. Paleta de colores (tema oscuro actual)

Los colores viven como variables CSS en `:root` dentro de `index.html`.
**Nunca escribas colores sueltos en el código nuevo — usa las variables.**

| Variable | Hex | Uso |
|---|---|---|
| `--bg` | `#0b0a09` | Fondo general de página |
| `--bg2` | `#12100e` | Fondo del drawer (carrito) |
| `--panel` | `#171412` | Fondo de tarjetas (base) |
| `--panel2` | `#1e1a16` | Fondo de tarjetas (parte alta del gradiente) |
| `--line` | `#2a2521` | Bordes sutiles |
| `--line2` | `#3a332c` | Bordes visibles / inputs |
| `--text` | `#eee9e1` | Texto principal |
| `--muted` | `#a1968a` | Texto secundario |
| `--dim` | `#6e655a` | Texto terciario / pistas |
| `--amber` | `#c98a3d` | Acento ámbar (botón dorado, focus) |
| `--amber2` | `#a86f2c` | Ámbar oscuro (gradientes) |
| `--gold` | `#d2a75c` | Oro: precios, acentos de lealtad |
| `--red` | `#a03530` | Rojo carne: CTA principal, ofertas |
| `--red2` | `#7f2723` | Rojo oscuro (gradientes) |
| `--green` | `#5fb878` | Éxito / estado "listo" |
| `--wood` `--wood2` `--wood3` | `#3b2a1d` `#4a3423` `#2b1f15` | Textura de madera del menú de categorías |
| `--steel1..4` | `#f2f2f0 → #5f5d5a` | Gradiente "acero" del logo |

Jerarquía de acentos: **rojo** = acción de compra · **ámbar/oro** = valor y recompensa · **verde** = confirmación y WhatsApp.

---

## 4. Tipografía

| Rol | Fuente | Cómo se usa |
|---|---|---|
| Display (títulos, botones, tags) | **Archivo** (Google Fonts) 700–900 | SIEMPRE mayúsculas + letter-spacing `.05–.2em`. Clase `.disp` |
| Texto | **Inter** 400–700 | 15px base, line-height 1.6 |

Escala aproximada: h1 hero 44–54px · h2 sección 26–30px · título de tarjeta 15px/700 · texto 13–14px · metadatos 11–12.5px.

**No introducir fuentes nuevas** sin decisión consciente — dos familias es el máximo.

---

## 5. Layout y componentes

- Contenedor máximo: **1240px**, padding lateral 22px (14px en móvil)
- Radio de esquinas: **12px** (`--r`) en tarjetas, 9–10px en botones, 999px en pastillas
- Grid de productos: `repeat(auto-fill, minmax(250px,1fr))`, gap 16px; en móvil 2 columnas
- Tarjeta de producto: imagen 160px + cuerpo (nombre / descripción corta / precio + botón)
- Botones: `.btn-r` rojo (comprar) · `.btn-p` ámbar (acción secundaria destacada) · `.btn-g`/`.btn-s` fantasma · `.btn-w` verde (WhatsApp)
- Barra de categorías: textura de madera, sticky, subrayado dorado en activa
- El sitio es **un solo archivo** `index.html` (CSS + JS incluidos). Mantenerlo así

---

## 6. Voz y copy

- **Idioma primario: español salvadoreño.** El inglés es traducción (objeto `T` en el código, claves `es`/`en` — toda palabra visible nueva necesita ambas)
- Frases cortas. Confianza tranquila, sin gritar
- Local y concreto: "puyazo para la carne asada", "chicharrón preparado con receta de la casa"
- Precios siempre con unidad: `$4.99 / lb`, `$29.99 / pack`
- Prohibido: "¡increíble!", "el mejor de la ciudad", "experiencia gastronómica única"

---

## 7. Imágenes (el paso más importante)

Cuando tengas fotos reales:

- **Estilo:** cortes sobre tabla de madera oscura, papel de carnicero o piedra; luz cálida lateral; fondo oscuro que funda con `--panel`
- **Formato:** JPG ~1200×900 (4:3), < 200 KB c/u (comprimir en tinypng.com)
- **Consistencia:** todas las fotos con la misma luz y el mismo fondo — eso da el look profesional de T&G
- En el repo: carpeta `img/`, nombres simples (`ribeye.jpg`, `chorizo.jpg`)
- En el código: el producto lleva `photo: "img/ribeye.jpg"` y la ilustración SVG queda de respaldo si no hay foto

---

## 8. Reglas técnicas al editar

1. Un solo archivo `index.html` — no dividir en varios archivos
2. No usar `localStorage` (el estado vive en memoria, objeto `S`)
3. Todo texto visible pasa por el objeto de traducciones `T` (es/en)
4. Los productos viven en el array `PRODUCTS`; las recetas en `RECIPES`
5. Respetar `prefers-reduced-motion` en cualquier animación nueva
6. Probar en móvil (390px) antes de subir — el header, carrito y catálogo ya son responsive
7. Subir a GitHub = Vercel publica solo (~30 s)
