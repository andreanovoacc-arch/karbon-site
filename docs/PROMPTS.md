# KARBÓN — Biblioteca de prompts

Prompts listos para copiar y pegar cuando quieras que una IA (Claude, etc.) edite el sitio.

## Cómo usar (siempre igual)

1. Abre un chat nuevo y **adjunta dos archivos**: `index.html` (del repo) y `docs/DESIGN-SYSTEM.md`
2. Pega UNO de los prompts de abajo (un cambio por conversación = mejores resultados)
3. Pide siempre el archivo completo de vuelta (los prompts ya lo dicen)
4. Prueba el archivo: ábrelo en tu navegador, revisa también en tamaño celular
5. Súbelo a GitHub (repo `karbon-site` → `index.html` → botón de editar/upload → commit) — Vercel publica solo

**Reglas que protegen tu sitio** (ya incluidas en cada prompt):
- Todo en un solo `index.html`
- Español + inglés para cualquier texto nuevo
- Sin `localStorage`
- No inventar datos del negocio

---

## P1 — Poner los datos reales del negocio

```
Adjunto index.html y DESIGN-SYSTEM.md de mi sitio (carnicería KARBÓN).
Reemplaza los datos placeholder por los reales, en TODOS los lugares donde aparecen
(header, sección Nuestra tienda, footer, checkout, factura, y el número de WhatsApp
en la constante WA_NUM):

- WhatsApp / teléfono: [TU NÚMERO, ej. +503 XXXX-XXXX]
- Dirección: [TU DIRECCIÓN EXACTA]
- Horario: [ej. Lun–Vie 8–6, Sáb 7–5, Dom 7–1]
- Email: [TU EMAIL]
- Enlace de Google Maps: [PEGA EL ENLACE DE TU UBICACIÓN]
- Año de fundación real: [AÑO] (si no quieres mostrarlo, quita "Est. 2026")
- Quita o corrige cualquier cifra inventada (ej. "1,200+ clientes").

No cambies nada más del diseño. Devuélveme el index.html COMPLETO en un solo archivo,
con los textos en español y en inglés actualizados (objeto T).
```

## P2 — Cambiar productos y precios reales

```
Adjunto index.html y DESIGN-SYSTEM.md. Los productos viven en el array PRODUCTS.
Actualízalo con mi lista real (mantén el formato del array, con nombre y descripción
en español e inglés, precio por lb o por pack, y categoría res/cerdo/pollo/emb/pack):

[PEGA TU LISTA, ej.:
- Puyazo — $5.25/lb — favorito para carne asada — categoría res
- Lomo de aguja — $4.10/lb — para guisos — categoría res, en OFERTA a $3.75
- ...]

Elimina los productos que no vendo: [LISTA].
Si una receta usaba un producto eliminado, ajústala al corte más parecido.
No cambies el diseño. Devuélveme el index.html COMPLETO.
```

## P3 — Agregar fotos reales (el cambio más importante)

```
Adjunto index.html y DESIGN-SYSTEM.md. Ya subí fotos reales de mis cortes al repo,
en la carpeta img/ con estos nombres: [ej. ribeye.jpg, puyazo.jpg, chorizo.jpg ...]

Modifica las tarjetas de producto, las recetas y las tarjetas del carrito para que:
1. Cada producto pueda tener una propiedad photo: "img/archivo.jpg"
2. Si el producto tiene foto, se muestre la foto (object-fit: cover, llenando el área
   de imagen de la tarjeta) — si no tiene, se mantenga la ilustración SVG actual
3. Asigna las fotos que te listé a sus productos
Sigue la sección "Imágenes" del DESIGN-SYSTEM.md. No cambies nada más.
Devuélveme el index.html COMPLETO.
```

## P4 — Hacer que el texto suene humano (anti-IA)

```
Adjunto index.html y DESIGN-SYSTEM.md. Revisa TODOS los textos visibles del sitio
contra la sección 2 del DESIGN-SYSTEM.md ("Cómo evitar que se vea generado por IA")
y la sección 6 ("Voz y copy").

Reescribe lo que suene genérico o inflado, usando estos datos reales de mi negocio:
[CUENTA EN 3-5 LÍNEAS TU HISTORIA REAL: quién corta la carne, desde cuándo,
de dónde viene la res, qué te hace diferente, frases que usas con tus clientes]

Mantén frases cortas y el tono de "carnicero que sabe lo que hace, sin gritar".
Actualiza español E inglés (objeto T). No toques diseño ni funcionalidad.
Devuélveme el index.html COMPLETO.
```

## P5 — Reemplazar los emojis por íconos serios

```
Adjunto index.html y DESIGN-SYSTEM.md. El sitio usa emojis como íconos
(🏬 ♦ ▣ ⏱ ✉ 📍 etc.), lo que se ve poco profesional.
Reemplázalos por íconos SVG inline minimalistas de una sola línea (estilo lucide/feather,
stroke 1.5-2, currentColor, 16-20px), coherentes entre sí.
Cuidado: hay emojis dentro de strings de JavaScript (topbar, servicios, toasts,
botones) — reemplázalos ahí también. No cambies textos ni funcionalidad.
Devuélveme el index.html COMPLETO.
```

## P6 — Ajustar una sección específica

```
Adjunto index.html y DESIGN-SYSTEM.md. Quiero cambiar SOLO la sección [hero /
catálogo / recetas / planificador / lealtad / tienda / footer]:

[DESCRIBE EL CAMBIO CONCRETO, ej.: "quiero que el hero muestre una foto de fondo
(img/hero.jpg) con un degradado oscuro encima para que el texto se lea"]

Respeta la paleta y tipografía del DESIGN-SYSTEM.md. No toques otras secciones.
Devuélveme el index.html COMPLETO.
```

## P7 — Agregar una sección nueva

```
Adjunto index.html y DESIGN-SYSTEM.md. Agrega una sección de [ej. testimonios /
galería de fotos / preguntas frecuentes] en la página de inicio, entre
[sección] y [sección].

Contenido REAL (no inventes nada):
[PEGA EL CONTENIDO: citas reales de clientes con su nombre, o lista de preguntas...]

Debe verse parte del mismo sitio (paleta, tipografía, radios del DESIGN-SYSTEM.md),
tener textos en es/en, y verse bien en móvil. Devuélveme el index.html COMPLETO.
```

## P8 — Arreglar un problema

```
Adjunto index.html. Hay un problema: [DESCRIBE QUÉ HACES, QUÉ ESPERABAS,
QUÉ PASÓ — ej.: "al hacer clic en Confirmar pedido en el celular, no pasa nada"]

Encuentra la causa y arréglala cambiando lo MÍNIMO posible.
Explícame en 2 líneas qué estaba mal. Devuélveme el index.html COMPLETO.
```

## P9 — Auditoría "¿se ve hecho por IA?"

```
Adjunto index.html y DESIGN-SYSTEM.md. Actúa como director de arte exigente.
Revisa el sitio contra la sección 2 del DESIGN-SYSTEM.md y dime, en una lista
priorizada, las 10 cosas que más lo hacen ver "generado por IA" o poco profesional,
con la corrección concreta de cada una. NO cambies código todavía — solo el análisis.
```

---

## Consejos finales

- **Un prompt, un cambio.** Si pides 5 cosas, la IA hará 3 bien y romperá 2
- Guarda una copia del `index.html` que funciona antes de cada cambio grande
  (en GitHub esto es automático: cada commit es una copia — desde el historial
  del archivo puedes ver y restaurar versiones anteriores)
- Si un cambio salió mal, en GitHub abre el archivo → History → busca la versión
  buena → cópiala de vuelta
- El orden que más impacto tiene: **P1 (datos reales) → P3 (fotos) → P4 (copy) → P5 (íconos)**
