# SNT-Validacion-QR

Sistema de Validación mediante Código QR para el Sistema Nacional de Turnos (SNT). Optimiza el control de acceso a turnos y eventos mediante la lectura de códigos QR desde dispositivos móviles (tablets y celulares).

## Funcionalidades

- **Autenticación** vía Mi Argentina
- **Escaneo** de códigos QR con feedback visual inmediato
- **Validación** en tiempo real contra el sistema de recepción SNT
- **Estados visuales**: Ingreso, Lectura, Acceso Válido (verde) y Error de Acceso (rojo)

## Tecnologías

- HTML5 + CSS3 + JavaScript vanilla
- Librería QR (`html5-qrcode`)
- Integración con API REST de SNT y Redis

## Estructura

```
├── index.html                # Pantalla de inicio / login
├── pantalla-lectura.html     # Escaneo QR
├── pantalla-valido.html      # Confirmación exitosa
├── pantalla-error.html       # Error de validación
├── assets/
│   ├── css/                  # Estilos
│   ├── img/                  # Imágenes y SVGs
│   └── js/                   # Scripts
├── docs/                     # Documentación
└── backups/                  # Versiones previas
```
