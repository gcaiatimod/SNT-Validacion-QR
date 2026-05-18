# Sistema Nacional de Turnos (SNT)
## Sistema de Validación mediante Código QR

### 1. Propuesta y Objetivos
El sistema está diseñado para optimizar el proceso de control de entradas y turnos en diversos eventos o puntos de atención.

*   **Tecnología**: Validación mediante lectura de códigos QR.
*   **Trazabilidad**: Garantiza el seguimiento de datos en tiempo real.
*   **Interoperabilidad**: Integración directa con el módulo de recepción del Sistema Nacional de Turnos (SNT).
*   **Plataformas**: Interfaz optimizada específicamente para dispositivos móviles (tablets y celulares).

---

### 2. User Flow (Flujo de Usuario)
El proceso operativo para los agentes de control sigue la siguiente lógica:

1.  **Autenticación**: El agente inicia sesión obligatoriamente a través de **Mi Argentina**.
2.  **Validación de Acceso**: El sistema verifica si el agente tiene permisos para operar.
3.  **Pantalla de Escaneo**: Se activa la cámara del dispositivo para capturar el código QR del ciudadano.
4.  **Procesamiento de Datos**:
    *   Si la lectura es exitosa, la información se envía al sistema de recepción (**REDIS**).
    *   Se impacta la **Base de Datos de SNT**.
5.  **Resultado Final**: El turno o entrada se marca como **Finalizado** y el sistema queda listo para el próximo escaneo.

---

### 3. Instancias y Estados del Sistema
La aplicación cuenta con estados visuales claros para facilitar la operación rápida:

| Estado | Descripción | Visualización |
| :--- | :--- | :--- |
| **Ingreso** | Pantalla inicial de bienvenida. | Botón de acceso con Mi Argentina. |
| **Lectura** | Cámara activa para escaneo. | Recuadro de enfoque con guía visual. |
| **Acceso Válido** | **Éxito**. Validación confirmada. | Fondo verde, detalles del evento/sector y confirmación de recepción. |
| **Error de Acceso** | **Rechazo**. Problema con el código. | Fondo rojo, motivo del error (ej: "Código ya usado"). |

---

### Detalles Técnicos de la Interfaz
*   **Identidad Visual**: Alineada con la Secretaría de Innovación, Ciencia y Tecnología.
*   **Feedback Inmediato**: Tras una validación exitosa o un error, el sistema retorna automáticamente a la pantalla de escaneo para agilizar el flujo de personas.
