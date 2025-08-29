# Firmeza – Certificados Edición Limitada (15 unidades)

Sitio estático verificador para NFC/QR. Cada gorra se verifica con `?id=` y `k=`.

## Estructura
- `index.html`: página del certificado (lee `id` y `k` de la URL, valida contra `caps.json`).
- `caps.json`: datos de las 15 gorras (token, imagen, metadata).
- `assets/`: imágenes sin espacios ni mayúsculas.
- `.nojekyll`: evita que GitHub Pages procese con Jekyll.

## Despliegue en GitHub Pages
1. Sube todo a tu repo.
2. En Settings → Pages → Source: `Deploy from a branch` → Branch: `main` → `/ (root)`.
3. Obtén tu URL pública cuando termine el build.

## Formato de URL (NFC / QR)
- Si el token contiene `/` (ej. `exclusiva1/15`), codifícalo como `%2F`.
- Ejemplo:
  - `https://<usuario>.github.io/<repo>/?id=1&k=exclusiva1%2F15`

## Cambiar el tiraje
- Edita `TOTAL` en `index.html` (por defecto 15).
- Añade/edita entradas en `caps.json` y sube imágenes en `assets/`.

## Seguridad
- Tokens "bonitos" son fáciles de adivinar. Para más seguridad, usa mezcla:
  - `exclusiva1/15-9c9afdfd` y graba el NFC con ese token.
