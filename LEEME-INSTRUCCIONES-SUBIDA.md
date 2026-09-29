# SLEEP'N Activos — Landing de captación de propietarios/inversores
Instrucciones para subir la página a sleepn.eco

## 1. Qué es esto
Landing page estática (HTML + CSS puro, sin JavaScript ni backend) dirigida a
propietarios e inversores para captar activos en régimen de alquiler,
gestión o desarrollo. Sigue la identidad visual de sleepn.eco (colores,
tipografías Jost + DM Sans, logo real y logo B Corp).

Repositorio con el histórico de cambios (GitHub):
https://github.com/gorka-debug/sleepn_expansion

## 2. Contenido del paquete
```
index.html                          → página completa (HTML5 válido, listo para producción)
img/
  atocha-new-bedroom.jpg            → galería SLEEP'N Atocha
  atocha-new-lounge.jpg
  atocha-new-fireplace.jpg
  atocha-new-rooftop-lounge.jpg     → también usada como imagen de fondo del hero
  atocha-new-bathroom.jpg
  valencia-new-room.jpg             → galería SLEEP'N Valencia
  valencia-new-facade.jpg
  valencia-new-bathroom.jpg
  valencia-new-rooftop1.jpg
  valencia-new-reception.jpg
  logo-real.png                     → logotipo SLEEP'N (nav + footer)
  bcorp-logo.png                    → sello oficial B Corp (footer)
  lockup-mejor-cadena.png           → gráfico "Soñamos con ser la mejor cadena del mundo" (hero)
docs/
  sleepn-valencia-dossier.pdf       → dossier descargable de SLEEP'N Valencia
```
Peso total del paquete: **~9,3 MB** (el dossier PDF de Valencia es 6,4 MB de ese total).

## 3. Dónde subirlo
Recomendado: como página independiente en una ruta propia, por ejemplo:

- `https://sleepn.eco/activos/` (recomendado, coincide con el `<link rel="canonical">` ya puesto en el `<head>`)
- o `https://sleepn.eco/inmuebles/` si se prefiere esa nomenclatura

Pasos:
1. Crear esa carpeta en el servidor/CMS de sleepn.eco.
2. Subir `index.html` en la raíz de esa carpeta y las carpetas `img/` y `docs/` tal cual, respetando los nombres de archivo (el HTML los referencia en minúsculas y con esos nombres exactos).
3. Si la ruta final NO es `/activos/`, actualizar la etiqueta `<link rel="canonical" href="https://sleepn.eco/activos">` dentro de `index.html` (línea ~7) para que coincida con la URL real.
4. Enlazar esta página desde el menú principal o el footer de sleepn.eco (p. ej. "Propietarios e inversores" o "Activos").

## 4. Requisitos técnicos
- **Hosting estático**: no necesita PHP, Node ni base de datos. Cualquier servidor web o CDN sirve.
- **HTTPS**: obligatorio, ya que la tipografía se carga desde Google Fonts por `https://fonts.googleapis.com` (ver `<style>` al principio del archivo). Si sleepn.eco bloquea recursos externos, hay que permitir ese dominio o alojar las fuentes localmente.
- **Sin dependencias de JavaScript**: la página es 100% HTML/CSS, no requiere ningún framework ni build previo.
- Compatible con navegadores modernos (usa CSS Grid, `clamp()`, variables CSS). No se ha probado en Internet Explorer (no es necesario en 2026).
- Incluye ya `<meta name="viewport">`, por lo que el diseño responsive funciona en móvil sin configuración adicional.

## 5. Enlaces y datos de contacto incluidos en la página
Revisar que sigan siendo correctos antes de publicar:

| Elemento | Valor actual |
|---|---|
| Email de contacto (botones CTA) | `gonzalo@sleepn.eco` |
| Teléfono | `+34 635 881 281` |
| WhatsApp (texto, no es enlace de click-to-chat) | `+34 636 810 702` |
| Enlace "Ver sleepnatocha.com" | `https://sleepnatocha.com` |
| Descarga dossier Atocha | `https://sleepnatocha.com/files/DOSSIERv1.pdf` (externo, no incluido en este paquete) |
| Descarga dossier Valencia | `docs/sleepn-valencia-dossier.pdf` (sí incluido en este paquete) |
| Vídeo de inauguración | `https://sleepn.eco/uploads/SLEEPN_Inauguracion.mp4` (externo) |

**Nota:** el número de WhatsApp aparece como texto plano, no como enlace `wa.me`. Si se quiere que sea "click to chat" en móvil, cambiar en `index.html`:
```html
<div>WhatsApp: <b>+34 636 810 702</b></div>
```
por:
```html
<div>WhatsApp: <a href="https://wa.me/34636810702" target="_blank" rel="noopener"><b>+34 636 810 702</b></a></div>
```

## 6. Cifras mostradas (verificar antes de publicar)
La sección "Lo que conseguimos en SLEEP'N Atocha" muestra KPIs reales aportados
por el equipo (ocupación, ADR, ventas, GOP, EBITDA — cierre 2025). Confirmar
que siguen vigentes en el momento de publicar, ya que quedan fechados como
"cierre 2025" en el pie de esa sección.

## 7. Contacto para dudas técnicas sobre este archivo
Generado por Claude (Anthropic) a petición de Gorka Rosell (Director de
Operaciones, SLEEP'N). El historial completo de cambios está en el
repositorio de GitHub indicado arriba, con un commit por cada ronda de
revisión.
