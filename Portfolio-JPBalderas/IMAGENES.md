# Guía: imágenes y clips en tu portafolio

Todo vive en esta carpeta (la misma que `index.html`):

**`/Users/juan.pablo.balderas/Documents/Portfolio-JPBalderas`**

No edites el HTML para cada foto de Photographer; sí puedes pegar un link de Vimeo en un proyecto de Director.

---

## Estructura de carpetas

```
Portfolio-JPBalderas/
├── index.html
├── assets/
│   └── cv-juan-pablo-balderas-2026.pdf   ← CV (opcional subir a GitHub)
└── img/
    ├── director/
    │   ├── viuda/
    │   ├── longest/
    │   ├── cuerpo/
    │   ├── mascaras/
    │   └── revolucion606/
    └── photographer/
```

---

## 1. Director — imágenes (5 proyectos)

Abre **Finder** → `Documentos` → `Portfolio-JPBalderas` → `img/director/`. Dentro de cada carpeta guarda los archivos con **estos nombres exactos**:

### Viuda (`viuda/`)
| Archivo | Qué poner |
|---------|-----------|
| `hero.jpg` | Still principal o póster (si usas video embebido, puede ser opcional) |
| `bts1.jpg` | Foto de rodaje 1 |
| `bts2.jpg` | Foto de rodaje 2 |

### The Longest Min (`longest/`)
| `hero.jpg` | Imagen grande arriba |
| `still1.jpg` | Producción / boom |
| `still2.jpg` | Pirotecnia |
| `still3.jpg` | Rodaje |

### ¿Qué es el cuerpo sin la mente? (`cuerpo/`)
| `hero.jpg` | Toma final (grande) |
| `boceto.jpg` | Boceto dibujado |
| `referencia.jpg` | Foto referencia |
| `final.jpg` | Otra toma final |

### Fábrica de Máscaras (`mascaras/`)
| `hero.jpg` | Making of (vertical, grande) |
| `archivo1.jpg` | Archivo familiar 1 |
| `archivo2.jpg` | Archivo 2 |
| `archivo3.jpg` | Archivo 3 |

### Revolutiön 606 (`revolucion606/`)
| `hero.jpg` | Stills principal |
| `still1.jpg` · `still2.jpg` · `still3.jpg` | Más stills |

**Formatos:** `.jpg`, `.jpeg`, `.png`, `.webp`

**Exportar desde Canva/slides:** Archivo → Descargar → JPG o PNG. Redimensiona si pesa mucho (ideal &lt; 500 KB por imagen para web).

**Probar:** Abre `index.html` → Director → clic en el proyecto → recarga con `Cmd + R` si no aparece (caché).

---

## 2. Director — clips de video

Tres formas (elige una por proyecto):

### A) Vimeo o YouTube (recomendado para cortos completos)

1. Sube el video a Vimeo o YouTube.
2. Copia el link (ej. `https://vimeo.com/123456789`).
3. En `index.html`, busca el proyecto en `directorProjects` (Ctrl+F `id: 'viuda'`).
4. En la línea `heroEmbed`, pega el link entre comillas:

```javascript
heroEmbed: 'https://vimeo.com/123456789',
```

5. Guarda y recarga. El reproductor aparece en el recuadro grande (hero).

Puedes añadir `heroEmbed` a cualquier proyecto (`longest`, `cuerpo`, etc.) copiando esa misma línea.

### B) Archivo de video en tu carpeta (sin subir a Vimeo)

1. Exporta el clip como `hero.mp4` (o `hero.webm`).
2. Guárdalo en la carpeta del proyecto, ej. `img/director/viuda/hero.mp4`.
3. En `index.html`, cambia la primera entrada de `images`:

```javascript
images: ['hero.mp4', 'bts1.jpg', 'bts2.jpg'],
```

4. Deja `heroEmbed: ''` vacío.

**Nota:** Los MP4 pesados hacen lento GitHub Pages; mejor Vimeo para cortos largos.

### C) Solo imagen (sin reproducir video)

Usa `hero.jpg` como en la tabla y deja `heroEmbed: ''`.

---

## 3. Photographer — muchas fotos (opción A)

1. Exporta tus fotos.
2. Ponlas en `img/photographer/`.
3. Renómbralas en orden con **3 dígitos**:

```
001.jpg
002.jpg
003.jpg
...
050.jpg
```

Puedes mezclar `.png` o `.webp`. El sitio busca del 001 al 400 y muestra las que existan.

4. Abre la pestaña **Photographer** en el navegador (o recarga).

No hace falta tocar el HTML al añadir más fotos: solo sigue la numeración (`051.jpg`, etc.).

---

## 4. Researcher & Visualizer

Los pitch decks ya están enlazados (Google Slides). No subes PDF ni imágenes ahí: si editas el Slides, la web se actualiza sola.

---

## 5. CV en About

Coloca el PDF en:

`assets/cv-juan-pablo-balderas-2026.pdf`

Si cambias el nombre del archivo, actualiza el enlace en el HTML (busca `cv-juan-pablo-balderas-2026.pdf`).

---

## 6. Subir a GitHub

Sube **toda la carpeta Portfolio-JPBalderas**, no solo `index.html`:

- `index.html`
- `img/` (con tus fotos dentro)
- `assets/` (con el CV)

Si solo subes el HTML, verás placeholders y los Slides sí cargarán, pero no las fotos ni el PDF.

---

## Resumen rápido

| Qué quieres | Dónde |
|------------|--------|
| Fotos de un corto | `img/director/nombre-proyecto/*.jpg` |
| Video Vimeo/YouTube | `heroEmbed: 'link'` en `index.html` |
| Video local | `hero.mp4` en la carpeta + cambiar `images` |
| Galería de fotografía | `img/photographer/001.jpg`, `002.jpg`… |
| CV descargable | `assets/cv-juan-pablo-balderas-2026.pdf` |

---

## Fondos de escaneo (solo Home y Director)

Coloca los escaneos en `img/bg/` con **estos nombres exactos** (sin carpetas en el nombre):

| Archivo | Página |
|---------|--------|
| `home.jpg` | Inicio |
| `director.jpg` | Director (+ detalle de proyecto) |

**Importante (Mac):** al guardar, el archivo debe llamarse `home.jpg`, no `img:bg:home.jpg.JPG`. Si arrastras desde Finder, renombra en la carpeta si hace falta.

**About · Contact** no usa fondo. Ahí va tu retrato:

| `img/about/portrait.jpg` | Foto tuya (vertical, 3:4) |

Para ajustar qué tan visible se ve el escaneo, edita en `index.html` el objeto `pageBackgrounds` (`opacity` del scan, `scrim` del velo blanco). Valores típicos: opacity `0.15`–`0.28`, scrim `0.82`–`0.9`.
