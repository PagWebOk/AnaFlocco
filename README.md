# Flocco & Asociados — sitio web

Sitio estático. Sin dependencias, sin build, sin framework: se abre haciendo doble clic en `index.html`.

## Estructura

```
flocco-asociados/
├── index.html          Todo el contenido y las secciones
├── css/styles.css      Estilos (variables de color al inicio del archivo)
├── js/main.js          Nav, menú mobile, animaciones de entrada, formulario
├── assets/favicon.svg  Ícono de la pestaña
└── README.md
```

## Secciones

| id          | Qué es |
|-------------|--------|
| `#inicio`   | Hero con fondo animado (auroras, polvo y columnas, todo CSS) |
| `#areas`    | Las 9 áreas de práctica del flyer |
| `#estudio`  | Quiénes son, con los 4 valores |
| `#proceso`  | Los 4 pasos, de la consulta al cierre |
| `#faq`      | 7 preguntas frecuentes |
| `#contacto` | Datos + formulario |

## Dónde tocar cada cosa

**Colores** — `css/styles.css`, bloque `:root`. La paleta es gris carbón cálido de base, marrón de acento y blanco roto para el texto. Los que mueven la aguja son `--brown`, `--tan` y `--ink`; el resto son variaciones.

**Tipografías** — `Source Serif 4` para títulos y `Inter` para el resto, ambas de Google Fonts (se cargan desde el `<link>` de `index.html`). Elegidas de bajo contraste y peso 600-700 para que se lean sólidas y no finitas.

**Teléfono de WhatsApp** — está en dos lugares:
- `js/main.js`, constante `WA_NUMERO`
- `index.html`, buscar y reemplazar `5493417480459` (formato internacional sin `+` ni espacios)

**Email** — `js/main.js`, constante `EMAIL`, y buscar `consultas@floccoyasociados.com.ar` en `index.html`.

**Textos** — directamente en `index.html`. Están en castellano rioplatense y en tono cercano, a tono con el flyer.

## Cómo funciona el formulario

No hay backend. Al enviar, arma el mensaje con los datos cargados y abre WhatsApp (botón principal) o el cliente de correo (botón secundario). La validación es la nativa del navegador (`required` + `reportValidity()`).

Si más adelante querés que los mensajes lleguen solos a una casilla, la forma más barata es apuntar el `<form>` a un servicio tipo Formspree: se cambia una línea de HTML y se borra el handler del JS.

**Chequeo del armado del mensaje:** abrir `index.html#selftest` y mirar la consola (F12). Tiene que decir `selftest ok`.

## Datos que faltan confirmar

Están todos en [DATOS-PENDIENTES.md](DATOS-PENDIENTES.md), ordenados por prioridad y listos para pasarle al estudio.

Lo más urgente: hay tres datos **inventados** hoy publicados en el sitio — el email de contacto, la ciudad (deducida de la característica 341) y el horario de atención.

Cuando lleguen las fotos, el bloque "El estudio" usa hoy una ilustración vectorial de una balanza. Para poner una foto real, reemplazar el `<svg class="figure__art">` por `<img class="figure__art" src="assets/ana-flocco.jpg" alt="Dra. Ana Flocco">`.

## Publicar

Al ser estático, sirve cualquier hosting gratuito: subir la carpeta entera a Netlify, Cloudflare Pages o GitHub Pages. No hace falta compilar nada.
