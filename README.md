# El ojo de San Martín — sitio del portal

Sitio estático del portal de noticias **El ojo de San Martín** (Gral. San Martín, Buenos Aires). No necesita servidor ni base de datos: son archivos HTML + CSS que se publican gratis en GitHub Pages.

## Archivos

- `index.html` — portada del portal.
- `mundial-2026.html` — primera nota publicada (Mundial 2026).
- `styles.css` — diseño compartido por todas las páginas.
- `assets/og-default.png` — imagen de previsualización general (cuando se comparte la portada).
- `assets/og-mundial-2026.png` — imagen de previsualización de la nota del Mundial.

## Cómo publicarlo en GitHub Pages (tu caso)

Tu repositorio es `elojodesanmartin/elojodesanmartin` y está vacío. **Antes de subir los archivos, conviene renombrarlo** para que la dirección quede lo más limpia posible.

### Paso 0 (recomendado): renombrar el repositorio
GitHub tiene una regla: para que el sitio viva en la raíz `https://elojodesanmartin.github.io/`, el repositorio debe llamarse exactamente **`elojodesanmartin.github.io`**.

1. En tu repo, andá a **Settings** (Configuración).
2. En **Repository name**, cambiá `elojodesanmartin` por `elojodesanmartin.github.io` y confirmá. (Como está vacío, no se pierde nada.)

> Si decidís **no** renombrarlo y dejarlo como `elojodesanmartin`, el sitio igual funciona, pero la dirección será `https://elojodesanmartin.github.io/elojodesanmartin/` y vas a tener que ajustar las direcciones de las redes (ver el final de esta guía).

### Paso 1: subir los archivos
En el repo, **Add file → Upload files**, y arrastrá todo el contenido de esta carpeta respetando la estructura:

```
index.html
mundial-2026.html
styles.css
assets/og-default.png
assets/og-mundial-2026.png
```

Importante: la carpeta `assets` debe subirse con sus imágenes adentro. Si arrastrás la carpeta entera, GitHub mantiene la estructura. Confirmá con **Commit changes**.

### Paso 2: activar Pages
1. **Settings → Pages**.
2. En **Source**, elegí la rama `main` y la carpeta `/ (root)`. Guardá.
3. Esperá un minuto y recargá. Tu sitio quedará en **https://elojodesanmartin.github.io/**.

Las direcciones de previsualización para redes ya están cargadas con ese dominio, así que no tenés que tocar nada más. ✅

---

### Si NO renombrás el repositorio
Si lo dejás como `elojodesanmartin`, el sitio será `https://elojodesanmartin.github.io/elojodesanmartin/`. En ese caso, en el `<head>` de `index.html` y `mundial-2026.html` agregá `/elojodesanmartin` después del dominio en las líneas `og:url`, `og:image` y `twitter:image`. Por ejemplo:
`https://elojodesanmartin.github.io/elojodesanmartin/assets/og-mundial-2026.png`

## Cómo agregar una nota nueva

1. Duplicá `mundial-2026.html` y renombralo, por ejemplo `obras-avenida.html` (usá nombres en minúscula, sin espacios ni acentos).
2. Editá dentro del archivo: el `<title>`, el `kicker` (la sección), el `<h1>` (título), la bajada (`dek`), la firma y el cuerpo (`body`). El diseño se mantiene solo.
3. En `index.html`, sumá la nota a la grilla copiando un bloque `<a class="card" ...>` y apuntando el `href` a tu archivo nuevo. Para destacarla arriba, reemplazá el bloque `<section class="lead">`.

### Secciones disponibles (para el kicker)
San Martín · Política · Deportes · Interés general · Cultura · Opinión · Comunidad

## Que las notas aparezcan con foto al compartirlas en redes

Cuando pegás un enlace en WhatsApp, Facebook o X, la red lee unas etiquetas especiales del HTML (Open Graph) para mostrar título, descripción y **una imagen de previsualización**. Ya están puestas y configuradas con tu dominio (`https://elojodesanmartin.github.io`) en `index.html` y en `mundial-2026.html`. No tenés que tocar nada, salvo que decidas no renombrar el repositorio (ver la guía de publicación más arriba).

La imagen que se muestra es la que figura en `og:image`: la portada usa `assets/og-default.png` y la nota del Mundial usa `assets/og-mundial-2026.png`.

### Imagen propia para cada nota nueva
Lo ideal es una imagen por nota, de **1200 × 630 píxeles** (es el tamaño que mejor se ve en todas las redes). Tenés dos caminos:

- **Foto real:** subí la foto a la carpeta `assets/` y apuntá las etiquetas `og:image` y `twitter:image` de esa nota a `https://TU-SITIO/assets/tu-foto.jpg`. Procurá que tenga proporción 1200×630 para que no se recorte.
- **Tarjeta de diseño:** las dos imágenes que ya vienen (`og-default.png` y `og-mundial-2026.png`) están hechas con la identidad del portal. Puedo generarte una así por cada nota nueva con su título; solo pedímelo.

> **Tip:** después de publicar o cambiar una imagen, las redes guardan la versión vieja en caché. Para forzar la actualización usá el *Sharing Debugger* de Facebook o el *Post Inspector* de LinkedIn, que vuelven a leer la página.

## Sobre el diseño

- **Identidad:** logo de "ojo / sol de mayo" que conecta con San Martín; paleta papel crema + tinta navy + oro.
- **Tipografías:** Fraunces (títulos) y Newsreader (texto), con Archivo para etiquetas. Se cargan desde Google Fonts, así que el sitio necesita conexión para verse igual.
- Los bloques de color de las imágenes son **marcadores de posición**. Cuando tengas fotos propias, se reemplazan fácil por etiquetas `<img>`. Pedímelo y te dejo la versión con foto.
- Las notas de la grilla marcadas como "Nota de ejemplo" son de muestra para que veas cómo queda la portada llena; reemplazalas por contenido real.

## Sugerencias para más adelante

- Dominio propio (ej. `elojodesanmartin.com.ar`) apuntando a GitHub Pages.
- Logo en `favicon` y para compartir en redes (imagen Open Graph).
- Una página "Quiénes somos" y formulario de contacto.
