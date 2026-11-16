# Registro de cambios

Herramienta web de un solo archivo para apuntar, por cada proceso editado:
nombre e ID del proceso, pestañas y contenidos (título + ID), qué se ha modificado y las capturas.
Después se pasa todo a Confluence con **Pegado paso a paso**, que copia por turnos el texto y cada captura.

## Publicarla con GitHub Pages

1. En GitHub: **New repository** → nombre `registro-cambios` → Public → Create.
2. **Add file → Upload files** → sube `index.html` (y este README) → Commit.
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main` / `(root)` → Save.
4. En 1–2 minutos estará en `https://TU-USUARIO.github.io/registro-cambios/`. Guárdala en marcadores.

## Uso

- Estructura: **Proceso (papá)** con nombre e ID → **Pestañas** (título e ID) → **Contenidos** de cada pestaña (título, ID, qué se ha modificado y capturas). También hay contenidos «sin pestaña», que cuelgan directamente del proceso.
- **↻ Nuevo registro de este mismo proceso** crea un registro nuevo con el mismo nombre e ID de proceso.
- **Ctrl+V** con una captura en el portapapeles la añade al elemento marcado en naranja (el último en el que hiciste clic).
- Si pegas en el título un texto «Título⇥ID» (copiado de una tabla), se separa solo en título e ID.
- **+ Varias desde una lista**: pega varias líneas «Título⇥ID» y crea un elemento por cada una.
- **Pegado paso a paso**: botón (o Enter) → Ctrl+V en Confluence → vuelve y repite.
- **Copiar todo**: texto y capturas de golpe (solo si Confluence acepta imágenes pegadas así).
- Atajos: `Alt+P` nueva pestaña, `Alt+C` nuevo contenido.

## Guardar en Google Sheets (con usuario y contraseña)

Se hace una sola vez:

1. Crea una hoja nueva en Google Sheets, por ejemplo «Registro de cambios».
2. En la hoja: **Extensiones → Apps Script**. Borra lo que aparece, pega todo el contenido de `Code.gs` y cambia arriba `USUARIO` y `CONTRASENA`. Guarda (icono del disquete).
3. **Implementar → Nueva implementación** → en el engranaje elige **Aplicación web**:
   - Ejecutar como: **Yo**
   - Quién tiene acceso: **Cualquier usuario** (la contraseña es la que protege los datos)
4. Pulsa **Implementar** y autoriza el acceso. Google avisa de que la app no está verificada porque es tuya: **Configuración avanzada → Ir a … (no seguro)** → Permitir.
5. Copia la **URL de la aplicación web** (acaba en `/exec`).
6. En la herramienta: **☁ Google Sheets** → pega la URL, tu usuario y tu contraseña → **Entrar**. La sesión dura 30 días.

Uso:

- **☁ Guardar en Google** sube las capturas nuevas a la carpeta de Drive «Registro de cambios - capturas» y escribe en la pestaña **Registros** una fila por cada contenido: fecha, proceso, ID, pestaña, ID, contenido, ID, cambios y enlaces a las capturas.
- Si vuelves a guardar el mismo registro, sus filas se sustituyen (no se duplican) y las capturas ya subidas no se vuelven a subir.
- Abajo a la izquierda ves si el registro tiene cambios sin guardar en Google.
- En **☁ Google Sheets** tienes la lista de todo lo guardado; haz clic en un registro para abrirlo en la herramienta, con sus capturas, desde cualquier ordenador.
- Si cambias algo en `Code.gs`: **Implementar → Gestionar implementaciones → ✏️ → Versión: nueva versión**. La URL no cambia.

## Dónde se guardan los datos

En el navegador donde la usas (IndexedDB) y, cuando pulsas **☁ Guardar en Google**, en tu hoja y en tu Drive. Nunca se sube nada a GitHub: allí solo está la página.
Si borras los datos del navegador, se pierden: usa **Exportar** de vez en cuando para tener una copia (.json) y **Importar** para recuperarla o llevarla a otro equipo.
