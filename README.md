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

- **Ctrl+V** con una captura en el portapapeles la añade al elemento marcado en naranja (el último en el que hiciste clic).
- Si pegas en el título un texto «Título⇥ID» (copiado de una tabla), se separa solo en título e ID.
- **+ Varias desde una lista**: pega varias líneas «Título⇥ID» y crea un elemento por cada una.
- **Pegado paso a paso**: botón (o Enter) → Ctrl+V en Confluence → vuelve y repite.
- **Copiar todo**: texto y capturas de golpe (solo si Confluence acepta imágenes pegadas así).
- Atajos: `Alt+P` nueva pestaña, `Alt+C` nuevo contenido.

## Dónde se guardan los datos

Solo en el navegador donde la usas (IndexedDB). No se sube nada a GitHub ni a ningún servidor.
Si borras los datos del navegador, se pierden: usa **Exportar** de vez en cuando para tener una copia (.json) y **Importar** para recuperarla o llevarla a otro equipo.
