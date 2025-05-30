Markdown → PDF & DOCX + GitHub Pages




TL;DR Pon tu Markdown en docs/, haz push, y conseguirás PDF + DOCX maquetados y una página con botones de descarga en segundos.

✨ Qué hace este proyecto

Función

Detalle

Compila

Convierte cada *.md en PDF (LaTeX) y DOCX usando Pandoc dentro de un contenedor.

Publica

Copia los archivos generados a la rama gh‑pages y los sirve mediante GitHub Pages.

Autogenera interfaz

Crea un index.html responsive (Bootstrap 5) con tarjetas y botones de descarga.

CI/CD completo

Todo se dispara en cada push a main o vía botón “Run workflow”.

Parametrizable

Cambia las carpetas de entrada/salida modificando solo dos variables en el YAML.

🚀 Cómo empezar en 30 segundos

# 1 — Clona el repositorio plantilla
git clone https://github.com/fermarfer1982/md-to-pdf-action.git
cd md-to-pdf-action

# 2 — Escribe o copia tus .md en la carpeta docs/
echo "# Hola Mundo" > docs/ejemplo.md

# 3 — Primer commit
git add .
git commit -m "docs: primer markdown"
git push -u origin main

Abre la pestaña Actions y espera el ✅.

Tu sitio estará en https://fermarfer1982.github.io/md-to-pdf-action/.

Tip: si es la primera vez, habilita Settings → Pages → Deploy from a branch → gh-pages.

⚙️ Personalizar rutas

La sección env: del workflow expone dos variables:

env:
  DOC_DIR: docs        # carpeta con los Markdown
  OUT_DIR: dist        # carpeta donde se crean PDF/DOCX e index.html

Para usar src/md/ y public/ basta con editar esas dos líneas; no toques nada más.

🗂 Estructura de carpetas

md-to-pdf-action/
├─ docs/           ⇦ archivos .md de entrada
├─ dist/           ⇦ (autogenerado) PDF, DOCX e index.html
└─ .github/
   └─ workflows/
       convert.yml  ⇦ pipeline completo

🛠 Workflow en resumen

flowchart TD
  A[Push a main] --> B[GitHub Actions]
  B --> C[Contenedor pandoc/latex]
  C --> D[Convierte .md → PDF+DOCX]
  D --> E[Genera index.html]
  E --> F[Publica OUT_DIR a gh-pages]
  F --> G[GitHub Pages]

✏️ Próximos pasos (ideas)

Añadir linter markdownlint antes de compilar.

Plantillas LaTeX corporativas (templates/ + --template).

Cron semanal para informes periódicos (on.schedule).

Notificación Slack/Teams con webhook.

🪪 Licencia

MIT © 2025 Fermarfer1982
