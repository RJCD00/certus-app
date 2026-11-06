# Certus — maqueta de app (Android)

Maqueta **visual** (no funcional) hecha como PWA: se instala en el celular con el ícono
y el nombre **Certus**, muestra la animación de carga y la pantalla de Inicio.

## Qué incluye
- **Ícono + nombre "Certus"** en la pantalla de inicio del celular.
- **Splash de carga (~30 s):** el logo se agranda y achica, y abajo sube el `Cargando: %` + `v.1.9.0`.
- **Inicio:** carrusel "CERTUS te mantiene informado" (4 banners en bucle, deslizable),
  las 3 tarjetas azules (Conoce tu sede / Mi fecha de pago / Medios de pago) y
  **"Las fijas"** (se ve bajando y se desliza de lado).
- **Mis cursos / Calendario / Finanzas / Menú:** pantallas en blanco (pendientes).

## Cómo instalarla en tu Android (elige una opción)

### Opción A — Netlify Drop (la más rápida, sin cuenta de dev)
1. Entra a **https://app.netlify.com/drop** desde la PC.
2. Arrastra **toda la carpeta `certus-app`** a esa página. Te da un enlace `https://...netlify.app`.
3. Abre ese enlace en **Chrome del celular** → menú **⋮** → **Instalar app / Agregar a pantalla de inicio**.
4. Aparece **Certus** con su ícono. Ábrela y verás la carga y el Inicio.

### Opción B — GitHub Pages (tú ya usas GitHub)
1. Crea un repo y sube el contenido de `certus-app`.
2. **Settings → Pages →** Branch: `main`, carpeta `/root` → **Save**.
3. Abre la URL `https://<usuario>.github.io/<repo>/` en Chrome del celular → **Instalar app**.

> Para que se instale con ícono y a pantalla completa necesita abrirse por **https** (opción A o B).
> Si solo abres el `index.html` desde los archivos, se ve la app pero no se instala con ícono propio.

## Estructura
```
certus-app/
├─ index.html              (toda la app: splash, inicio, pestañas, navegación)
├─ manifest.webmanifest    (nombre "Certus" + íconos)
├─ sw.js                   (service worker: offline + instalable)
└─ img/                    (ícono, logo, banners, tarjetas y miniaturas)
```

## Ajustes rápidos
- **Duración del splash:** en `index.html`, variable `SPLASH_MS` (30000 = 30 s).
- **Velocidad del carrusel:** en el `setInterval(..., 4000)` (4 s por banner).
