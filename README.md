# La Virginia · Condominio campestre

Sitio web del condominio campestre La Virginia (El Retiro, Antioquia): plano interactivo de los 16 lotes, ficha de cada lote con fotos reales, diferenciales del proyecto, ficha técnica, avance de obra, galería, ubicación y contacto por WhatsApp.

## Estructura

```
index.html    Página completa (HTML, CSS y JS en un solo archivo)
lotes.json    Datos de los lotes: estado, precio, área, fotos y características
img/          Fotos reales, renders y plano de urbanismo
vid/          Videos cortos del recorrido y sus portadas
```

## Cómo actualizar los lotes

Todo lo comercial está en `lotes.json`; no hay que tocar el diseño.

- **Estado:** `"estado"` acepta `disponible`, `reservado`, `vendido` o `no_disponible`.
- **Precio:** `"precio"` en pesos, sin puntos (ej. `645000000`). Vacío o `null` muestra "Consultar".
- **Fotos:** lista de rutas dentro de `img/` en `"fotos"`.
- **Fecha:** cambie `"actualizado"` (AAAA-MM-DD) cada vez que actualice la disponibilidad.
- **WhatsApp:** en `"config"` → `"whatsapp"`, el número con indicativo y sin espacios (ej. `573001234567`).

`index.html` trae una copia de respaldo de los datos; si `lotes.json` carga, la página usa siempre `lotes.json`.

## Publicación

El sitio está publicado en **https://lavirginiacondominio.com** con Cloudflare Pages (proyecto `la-virginia-web`). Cada commit a `main` se publica solo en uno o dos minutos. El dominio está registrado en Cloudflare Registrar.

## Publicar con GitHub Pages (alternativa)

Settings → Pages → Source: *Deploy from a branch* → Branch: `main` / carpeta `/ (root)`.
El sitio queda en `https://<usuario>.github.io/<repositorio>/`. Para usar `condominiolavirginia.com`, agregue el dominio en la misma pantalla y configure el DNS según las instrucciones de GitHub.

## Ver en local

```
python3 -m http.server 8000
```
y abra http://localhost:8000 (abrir el archivo con doble clic no carga `lotes.json`).
