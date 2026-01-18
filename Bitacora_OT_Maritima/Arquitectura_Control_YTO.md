# ⚓ Bitácora OT: Arquitectura de Control Distribuido (YTO)

**Sistema:** Propulsión Principal
**Modelo de Motor:** YTO YM6S4WF-C-11
**Controladores:** Panel Digital Local (Sala de Máquinas) + Panel Remoto (Puente de Mando)

## 📡 Diagrama de Conectividad (Capa Física - Layer 1)
- **Tipo de Enlace:** Conexión cableada punto a punto (Hardwired Analog Multi-core).
- **Medio de Transmisión:** Cable multipar con conectores de aviación/militares en los extremos.
- **Protocolo:** No aplica (Señalización eléctrica analógica pura: 0-10V / 4-20mA / Resistiva).

## 🛡️ Perfil de Ciberseguridad
- **Inmunidad Digital:** Alta. Al no utilizar protocolos TCP/IP ni buses de datos seriales, este enlace es inmune a ciberataques remotos (Ransomware/Malware). Es un sistema "Air-gapped" por naturaleza física.
- **Vulnerabilidad Física:** Alta. La seguridad depende enteramente de la integridad física del cableado. Un atacante con acceso físico podría interceptar o falsificar señales individuales interviniendo los pines específicos del conector.


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
