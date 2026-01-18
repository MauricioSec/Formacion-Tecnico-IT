# ⚓ Bitácora IT: Infraestructura de Comunicaciones y Navegación

**Fecha:** 19/01/2026
**Ubicación:** Puente de Mando

## 📡 Inventario de Conectividad (Capa de Red)
1.  **Proveedor ISP:** Starlink (Satellital LEO).
    -   **Estado:** Señal Wi-Fi interna óptima (RSSI alto), pero enlace WAN inestable/lento (Latencia alta o Packet Loss).
    -   **Diagnóstico Preliminar:** Posible saturación de ancho de banda o ubicación física de la antena con obstrucciones parciales.
2.  **Redundancia:** Red Móvil (Celular 4G/5G) y Radio VHF (Voz Analógica).

## 🗺️ Sistemas de Navegación (Tecnología Operacional)
-   **Posicionamiento:** GPS Garmin (Grado Comercial).
-   **Cartografía:** Cartas de Navegación Electrónicas (Electronic Charts).
-   **Riesgo Identificado:** La inestabilidad de la conexión a internet podría comprometer la actualización oportuna de las cartas de navegación (Availability & Integrity).

## 🛡️ Análisis de Seguridad
-   **VHF:** Medio no seguro (Texto claro/Voz abierta). No apto para transmitir información sensible.
-   **Starlink:** Al ser la puerta de enlace principal, debe estar segurizada (WPA3 en el Wi-Fi) para evitar que dispositivos no autorizados consuman el ancho de banda crítico.

---
> *Observación: Se recomienda auditar la ubicación de la antena Starlink y gestionar el ancho de banda (QoS) para priorizar la navegación sobre el ocio.*
> 
