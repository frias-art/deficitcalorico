# Déficit — calorías con foto

App web para móvil que calcula tu objetivo de calorías para un déficit calórico seguro y estima las calorías de tus comidas a partir de una foto.

## Qué hay en esta carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La app completa |
| `manifest.json` | Permite instalarla en el móvil como una app (icono, nombre, pantalla completa) |
| `sw.js` | Hace que abra aunque no tengas conexión |
| `icons/` | Iconos de la app |
| `.nojekyll` | Le dice a GitHub Pages que publique los archivos tal cual |

## Publicarla en GitHub Pages

1. Entra en github.com y crea un repositorio nuevo, por ejemplo `deficit`. Puede ser público (GitHub Pages gratis lo exige en cuentas personales).
2. En el repositorio pulsa **Add file → Upload files** y arrastra **todo el contenido** de esta carpeta (incluida la carpeta `icons`). Pulsa **Commit changes**.
   - Si no ves el archivo `.nojekyll` al arrastrar (es un archivo oculto), no pasa nada: la app funciona igual.
3. Ve a **Settings → Pages**. En *Source* elige **Deploy from a branch**, rama **main** y carpeta **/ (root)**. Pulsa **Save**.
4. Espera 1-2 minutos. Tu app estará en `https://TU-USUARIO.github.io/deficit/`

## Instalarla en el móvil

- **Android (Chrome):** abre el enlace → menú ⋮ → **Instalar app** o **Añadir a pantalla de inicio**.
- **iPhone (Safari):** abre el enlace → botón Compartir → **Añadir a pantalla de inicio**.

## Activar el análisis de fotos con IA

Fuera de Claude, la app necesita tu propia clave de la API de Anthropic:

1. Entra en https://console.anthropic.com, crea una cuenta y añade algo de saldo (Billing).
2. Ve a **API Keys → Create Key** y copia la clave (empieza por `sk-ant-`).
3. En la app: **Perfil → IA para analizar fotos**, pega la clave y pulsa **Guardar**.

La clave se guarda solo en tu móvil y las fotos van directamente de tu móvil a Anthropic. Cada análisis cuesta unos céntimos. Sin clave puedes seguir usando la app con la opción **Manual**.

> Importante: el repositorio y la web son públicos, pero tu clave **no** está en ellos: solo vive en tu teléfono. No pongas nunca la clave dentro de los archivos del repositorio.

## Tus datos

Perfil, comidas y peso se guardan en el almacenamiento del navegador de tu móvil. No se envían a ningún servidor. Si borras los datos del navegador o cambias de móvil, se pierden.

## Actualizar la app

Sube el nuevo `index.html` al repositorio (sustituyendo el anterior) y cambia en `sw.js` la línea `const VERSION = "deficit-v1";` por `deficit-v2`, `deficit-v3`… para que los móviles descarguen la versión nueva.

---

Cálculo con la fórmula de Mifflin-St Jeor. Las estimaciones son orientativas y no sustituyen el consejo de un médico o dietista-nutricionista.
