# ⚓ Bitácora OT: Arquitectura de Control Distribuido (YTO)

**Sistema:** Propulsión Principal
**Modelo de Motor:** YTO YM6S4WF-C-11
**Controladores:** Panel Digital Local (Sala de Máquinas) + Panel Remoto (Puente de Mando)

## 📡 Diagrama de Conectividad (Network Topology)
Se identifica una red de comunicación industrial entre dos nodos:
1.  **Nodo A (Local - Tier 0):** Tablero en Sala de Máquinas. Tiene prioridad de control (Arranque/Parada).
2.  **Nodo B (Remoto - Tier 1):** Tablero en Puente. Función principal de telemetría (Visualización de datos para navegación).
3.  **Enlace (Link):** Cableado físico que transporta señales de sensores (RPM, Presión, Temp) hacia el puente. Indicado por el LED "REMOTE" en el panel.

## 🛡️ Análisis de Vulnerabilidad: "Ceguera del Operador"
El sistema depende de la confianza entre el Nodo A y el Nodo B.
- **Escenario de Riesgo:** Desconexión o corrupción de datos entre la sala y el puente.
- **Impacto Operativo:** El oficial de guardia pierde "Conciencia Situacional" (Situational Awareness). No sabría si el motor perdió presión de aceite o si se apagó, retrasando la respuesta ante emergencias.

## ⚙️ Actuadores Críticos (Physical Layer)
El sistema controla componentes electro-hidráulicos:
- **Embrague Hidráulico (KLT Series):**. Actúa como la interfaz final entre el motor y la hélice.
- **Bombas Hidráulicas Auxiliares:**. Alimentan sistemas de cubierta (Grúa/Huinche).

---
> *Nota del Maquinista: La prioridad de mando siempre la tiene la Sala de Máquinas por seguridad (Local Override).*
> 
