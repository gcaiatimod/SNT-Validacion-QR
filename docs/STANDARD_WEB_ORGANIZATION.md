# Estándar de Organización para Proyectos Web Eficientes

Este documento establece la estructura base y las buenas prácticas para la organización de archivos, aplicable a cualquier proyecto de desarrollo web.

## 1. Arquitectura de Directorios (The "Assets" Standard)

La raíz del proyecto debe permanecer lo más limpia posible, delegando los recursos a subcarpetas específicas:

```text
/ (Raíz del Proyecto)
├── index.html              # Punto de entrada principal
├── [nombre-seccion].html   # Páginas o vistas secundarias
├── assets/                 # RECURSOS ESTÁTICOS (Obligatorio)
│   ├── css/                # Hojas de estilo unificadas
│   ├── img/                # Multimedia (imágenes, iconos, svgs)
│   ├── js/                 # Lógica de cliente y librerías
│   └── vendor/             # Librerías de terceros locales (si no se usan CDNs)
├── docs/                   # DOCUMENTACIÓN (MD, PDFs, Requerimientos)
│   ├── WORKFLOW.md         # Definición de flujos (usuario/datos)
│   ├── RULES.md            # Reglas de negocio y de código
│   └── *.md                # Otros documentos de referencia
└── backups/                # HISTORIAL (Versiones previas, templates originales)
```

## 2. Reglas de Oro de Estilo y Código

*   **CSS Externo Obligatorio**: Queda prohibido el uso de estilos inline o bloques `<style>` en el HTML. Todo debe centralizarse en `assets/css/`.
*   **Contextualización por Body Class**: Para proyectos multi-página con un solo CSS, se debe identificar cada página en el body: `<body class="page-home">`.
*   **Rutas Relativas Limpias**: Siempre usar rutas relativas consistentes: `assets/css/style.css`.
*   **Naming Kebab-Case**: Todos los archivos y carpetas deben nombrarse en minúsculas y separados por guiones (ej: `proceso-de-pago.html`).

## 3. Flujo de Trabajo en la Organización

Al iniciar o refactorizar un proyecto, los pasos obligatorios son:
1.  **Identificar el Core**: Definir cuál es la pantalla principal y renombrarla a `index.html`.
2.  **Encapsular Assets**: Mover todos los archivos `.css`, `.js` e imágenes a sus respectivas carpetas dentro de `assets/`.
3.  **Depurar la Raíz**: Mover cualquier archivo de referencia, borrador o template original a `backups/`.
4.  **Documentar el Origen**: Crear un archivo en `docs/` que explique brevemente de qué trata el proyecto y cómo se usa.

## 4. Beneficios del Estándar
*   **Escalabilidad**: Es fácil agregar nuevas secciones sin desordenar la raíz.
*   **Mantenibilidad**: Los estilos se modifican en un solo lugar.
*   **Portabilidad**: El proyecto es fácil de mover o subir a cualquier servidor (como LAMPP) sin romper rutas.
