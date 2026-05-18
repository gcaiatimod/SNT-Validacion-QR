# Guía de Estructura y Organización de Proyectos (Estándar SNT)

Esta guía define el estándar de organización de archivos y carpetas para proyectos web, basado en la optimización del Sistema de Validación QR.

## 1. Estructura de Carpetas

Todo proyecto debe seguir la siguiente jerarquía de directorios:

```text
/ (Raíz)
├── index.html              # Punto de entrada principal (antes pantalla-ingreso)
├── pantalla-*.html         # Pantallas independientes del flujo
├── assets/                 # Recursos estáticos del sitio
│   ├── css/                # Hojas de estilo externas (.css)
│   ├── img/                # Imágenes, iconos y referencias visuales
│   └── js/                 # Scripts externos (.js)
├── docs/                   # Documentación técnica y guías
│   └── *.md                # Archivos Markdown de referencia
└── backups/                # Respaldos de templates originales o versiones legacy
```

## 2. Convenciones de Nomenclatura

*   **Punto de entrada**: El archivo de inicio siempre debe ser `index.html`.
*   **Archivos HTML**: Usar nombres descriptivos en minúsculas y separados por guiones (kebab-case), ej: `pantalla-lectura.html`.
*   **Activos (Assets)**: Los nombres deben ser claros y reflejar su contenido, ej: `snt-validacion.css`, `logo-mi-argentina.png`.

## 3. Gestión de Estilos (CSS)

*   **Externalización**: No usar bloques `<style>` dentro del HTML. Todo el CSS debe residir en `/assets/css/`.
*   **Modularización por Body Class**: Para manejar estilos específicos de diferentes pantallas en un solo archivo CSS, asignar una clase única al `<body>`:
    ```html
    <!-- En pantalla-lectura.html -->
    <body class="page-lectura">
    ```
    ```css
    /* En el CSS global */
    .page-lectura .visor-camara { ... }
    ```
*   **Variables**: Definir un bloque `:root` con las variables de color, radios y fuentes del sistema de diseño para asegurar consistencia.

## 4. Documentación y Trazabilidad

*   Cada proyecto debe contar con un archivo de documentación en `/docs/` (ej: `SNT_QR_Validation.md`) que detalle:
    *   Objetivos del sistema.
    *   User Flow (Flujo de usuario).
    *   Estados de la interfaz (Éxito, Error, Lectura).
    *   Identidad visual aplicada.

## 5. Proceso de Limpieza y Reorganización

Al finalizar un desarrollo o prototipo:
1.  Mover templates de referencia o archivos "sucios" a `/backups`.
2.  Verificar que todas las rutas internas de `<link>`, `<a>` e `<img>` estén actualizadas a la nueva estructura de `/assets`.
3.  Asegurar que el `index.html` sea la pantalla de inicio funcional.
