# NEXUS ARENA (Entrega 2)

> Proyecto Intermodular · 2.º SMR · DAVANTE MEDAC JAÉN · Curso 2026/27  
> **Equipo 1** · Fecha límite de entrega: 27/11/2026

Repositorio oficial de diseño técnico, presupuesto, planos y prototipado de red para **NEXUS ARENA**, un centro de eSports y streaming con 12 puestos gaming, 2 boxes de streaming, recepción y zona de espectadores.

---

## Resumen Ejecutivo del Proyecto

| Parámetro | Especificación del Diseño |
| :--- | :--- |
| **Cliente** | NEXUS ARENA — Centro de eSports y Streaming |
| **Alternativa Elegida** | **Alternativa 2:** Segmentación por VLANs + Servidor Virtualizado + Enlace de respaldo 4G/5G |
| **Presupuesto Máximo** | 18.000,00 €  |
| **Presupuesto Cerrado** | 17.236,20 € (Base Imponible) · IVA 21 %: 3.619,60 € · Total con IVA: 20.855,80 € |
| **Costes Periódicos** | 28,00 € / mes |
| **Condición de Éxito** | Partida simulada activa sin interferencias ni mezcla de tráfico de invitados con la red interna |

---

## Equipo Técnico y Reparto de Responsabilidades

| Integrante | Rol en el Equipo | Perfil Técnico | Responsabilidad principal |
| :--- | :--- | :--- | :--- |
| **Pablo Lechuga Sánchez** | Coordinador | Coordinación y Finanzas | Control de presupuesto, seguimiento de estrategia y gestión de GitHub. |
| **Fede Espinosa Sánchez** | Investigación | Redes y Conectividad | VLANs, reglas de firewall, Wi-Fi y failover 4G/5G. |
| **Andrés Garrido López** | Portavoz | Sistemas y Virtualización | Hipervisor Proxmox VE, NAS, monitorización Uptime Kuma y copias. |
| **Adrián Aceituno Rodríguez** | Verificación | Calidad y Seguridad | Pruebas de aceptación, riesgos, fichas técnicas y fuentes. |

---

## Estructura del Repositorio

```text
📦 nexus-arena
 ┣ 📂 01_Documentacion
 ┃ ┣ 📜 Entrega 1 proyecto.pdf
 ┃ ┣ 📜 Entrega 2 proyecto.pdf
 ┃ ┗ 📜 Fichas_Individuales_Contribucion.pdf
 ┣ 📂 02_Diagramas_y_Planos
 ┃ ┣ 📜 Plano Fisico NexusArena.png
 ┃ ┣ 📜 Topologia Logica VLANs.png
 ┃ ┗ 📜 Diagrama de Bloques.png
 ┣ 📂 03_Presupuesto_e_Inventario
 ┃ ┣ 📜 Presupuesto E2 NexusArena 2026.xlsx
 ┃ ┗ 📜 Fuentes_y_Precios.txt
 ┣ 📂 04_Prototipo_PacketTracer
 ┃ ┗ 📜 Prototipo Red NexusArena v1.pkt
 ┗ 📜 README.md
```

---
