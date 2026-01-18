# ⚓ Bitácora OT: Falla Crítica en Generador Perkins 30 KVA

**Fecha:** 18/01/2026 (Aprox)
**Sistema:** Generación Eléctrica Auxiliar
**Componente Afectado:** Motor de Arranque (Starter Motor)
**Estado:** Inoperativo (A la espera de repuesto)

## 🚨 Descripción del Incidente
Durante la ronda de mantenimiento, el Generador Perkins de 30 KVA falló en el proceso de arranque (Boot Failure). Este equipo es crítico para el suministro eléctrico de la nave.

## 🛠️ Metodología de Diagnóstico (Troubleshooting)
Se aplicó un procedimiento de descarte lógico de fallas:

1.  **Inspección Nivel 0:** Verificación de fluidos (aceite/agua). Estado OK.
2.  **Hipótesis 1: Fallo de Alimentación (Batería).**
    - *Prueba:* Puente con batería auxiliar y cambio de batería.
    - *Resultado:* Negativo. El fallo persiste.
3.  **Hipótesis 2: Fallo Mecánico/Eléctrico en Sistema de Arranque.**
    - *Acción:* Extracción del componente (Motor de arranque) para pruebas en banco (fuera del sistema).
4.  **Pruebas de Componentes (Unit Testing):**
    - Se conectó tierra a carcasa y positivo a solenoide.
    - **Prueba A (Solenoide):** Al excitar el terminal de ignición, el solenoide acciona (Click auditivo). -> **Lógica de control OK.**
    - **Prueba B (Motor):** Al puentear directo el motor (bypasseando el solenoide), el inducido no gira. -> **Actuador Físico DAÑADO.**

[attachment_0](attachment)

## 💡 Análisis IT/Ciberseguridad (Lecciones Aprendidas)

### 1. Disponibilidad y Punto Único de Fallo (SPOF)
El motor de arranque actuó como un **Single Point of Failure**. Sin este componente pequeño, un sistema complejo de 30 KVA queda inútil.
* **Reflexión:** En un Data Center, esto se mitigaría con redundancia (otro generador listo para entrar automáticamente).

### 2. Validación de Diagnóstico (Peer Review)
El diagnóstico fue validado posteriormente por el mecánico especialista, quien replicó exactamente mis pasos y confirmó el resultado.
* **Reflexión:** Seguir protocolos estándar permite que cualquier técnico pueda reproducir el error y confirmar la solución. La documentación de los pasos es vital.

### 3. Seguridad Física
Se aplicó bloqueo de energía (baterías desconectadas) antes de manipular el componente para evitar arcos eléctricos o arranque intempestivo.

## ✅ Resolución
Se generó el reporte de falla a jefatura. El mecánico confirmó la necesidad de reemplazo. A la espera de la pieza nueva para restaurar el servicio (Mean Time To Repair - MTTR en curso).
