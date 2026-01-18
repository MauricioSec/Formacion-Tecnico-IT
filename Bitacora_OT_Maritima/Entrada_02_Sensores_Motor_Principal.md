# ⚓ Bitácora OT: Análisis de Sensores - Motor Principal YTO

**Fecha:** 19/01/2026
**Sistema:** Motor Principal YTO YM6S4WF-C-11 (Propulsión y PTO Hidráulico)
**Panel de Control:** Monitor Digital con Telemetría Local

## 👁️ Análisis del Sensor Crítico: Presión de Aceite (L.O. Press)

### 1. Funcionamiento Físico
- **Variable Real:** Presión del fluido lubricante dentro del bloque del motor.
- **Lectura Actual:** 0.52 MPa (Operación Normal).
- **Actuador:** Si la presión cae, el sistema mecánico sufriría fricción catastrófica (gripaje).

### 2. La Ruta del Dato (Digitalización)
1.  **Origen:** Un sensor piezorresistivo o bulbo de presión en el motor convierte la presión física en una señal eléctrica (voltaje/resistencia).
2.  **Procesamiento:** La ECU (Unidad de Control) o el Panel lee esa señal eléctrica.
3.  **Salida (HMI):** La pantalla muestra "0.52".

### 3. Escenario de Ciberseguridad (Integridad de Datos)
**El Ataque "Spoofing" (Falsificación):**
Si un atacante intercepta el cable del sensor o hackea el panel:
- **Escenario A (Falso Negativo):** El motor tiene aceite (0.5 MPa), pero el hacker inyecta una señal de "0 MPa".
    - *Consecuencia:* El sistema de protección automático ("Stop" LED) apaga el motor en plena maniobra. La nave queda a la deriva.
- **Escenario B (Falso Positivo):** El motor pierde aceite (rotura de manguera), pero el hacker fija el valor en "0.52 MPa" estático.
    - *Consecuencia:* El maquinista cree que todo está bien. El motor se funde por falta de lubricación sin que suene ninguna alarma.

### 4. Observación de Riesgo: "REMOTE"
El panel posee un indicador de estado **"REMOTE"**. Esto sugiere capacidad de recibir órdenes externas. En una auditoría de seguridad, se debe verificar si este puerto está conectado a alguna red y si está protegido con contraseña.

---
> *Evidencia adjunta: Fotos de lecturas en tiempo real y placa del fabricante.*
> 
