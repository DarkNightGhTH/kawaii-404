# 404 Kawaii Anime

Página de error 404 con estética kawaii/anime, lista para producción.
Un único archivo autocontenido (`404.html`): sin dependencias externas, sin peticiones a terceros, carga instantánea y cacheable.

## Características

- Gatito SVG animado (parpadeo, cola, brazo saludando) con burbuja de diálogo interactiva al hacer clic.
- Fondos flotantes (estrellas, corazones, nubes), parallax con el ratón y efecto "corazones" al tocar el gatito.
- Modo claro/oscuro automático (`prefers-color-scheme`).
- Accesibilidad: `aria-label` en el 404, foco visible, `prefers-reduced-motion` desactiva animaciones.
- Responsive (móvil primero) y metadatos SEO/OG incluidos.

## Despliegue (importante: servir con estado HTTP 404)

### Nginx

```nginx
error_page 404 /404.html;
location = /404.html {
    root /var/www/tu-sitio;
    internal;
}
```

### Apache

```apache
ErrorDocument 404 /404.html
```

### Netlify

Renombra el archivo a `404.html` en la raíz del directorio publicado (Netlify lo sirve automáticamente con estado 404).

### Vercel / Cloudflare Pages / GitHub Pages

Coloca `404.html` en la raíz del contenido estático (`public/` en Vercel). GitHub Pages sirve `404.html` automáticamente para rutas inexistentes.

### Headers recomendados

```nginx
add_header Cache-Control "public, max-age=3600" always;
```

## Personalización

- Título y descripción: etiquetas `<title>` y `<meta name="description">` del `<head>`.
- Enlace de inicio: atributo `href="/"` del botón primario.
- Frases del gatito: array `phrases` en el `<script>`.
- Colores: variables CSS de `:root` (`--pink`, `--purple`, `--sun`, fondos `--bg1..3`).
- Textos: `lang="es"` en `<html>`; cámbialo si el sitio usa otro idioma.

## Enlace público (GitHub Pages)

- Página 404 directa: https://darknightghth.github.io/kawaii-404/404.html
- Raíz del sitio: https://darknightghth.github.io/kawaii-404/ (las rutas inexistentes sirven esta página con estado HTTP 404)
