# 🎮 NEXUS ARENA (Entrega 2)

> Proyecto Intermodular 2.º SMR

Repositorio oficial de diseño técnico, presupuesto, planos y prototipado de red para **NEXUS ARENA**, un centro de alto rendimiento de eSports, entrenamiento competitivo y retransmisión en directo (Streaming).

---

## 🎯 Resumen Ejecutivo del Proyecto

| Parámetro | Especificación del Diseño |
| :--- | :--- |
| **Cliente** | NEXUS ARENA — Centro de eSports y Streaming |
| **Alternativa Elegida** | **Alternativa 2:** Segmentación lógica por VLANs (802.1Q) + Servidor Central Virtualizado (Proxmox VE) |
| **Presupuesto Máximo** | 18.000,00 € |
| **Presupuesto Cerrado** | **17.533,99 € (IVA 21% incluido)** — *Margen de ahorro: +466,01 €* |
| **Costes Periódicos (OPEX)** | **55,00 € / mes** (Fibra 1 Gbps Simétrica + Línea 4G/5G de Backup) |
| **Condición de Éxito** | Partida competitiva y streaming operando sin mezclar tráfico de invitados (VLAN 40 aislada por ACL) |

---

## 👥 Equipo Técnico y Reparto de Responsabilidades

| Integrante | Rol en el Equipo | Perfil Técnico (E2) | Tareas y Archivos Asociados |
| :--- | :--- | :--- | :--- |
| **Pablo Lechuga Sánchez** | Coordinador | Arquitecto de Redes y Coordinación | Topología lógica, tabla IP/VLANs, scripts Cisco IOS (`.pkt`) y gestión de GitHub. |
| **Fede Espinosa Sánchez** | Investigación | Admin. de Sistemas y Virtualización | Diseño del servidor `SRV-HV-01`, hipervisor, permisos de **Nextcloud** y backups RAID 1 + USB. |
| **Adrián Aceituno Rodríguez** | Verificación | Ingeniero QA, Monitorización y Seguridad | Panel **Uptime Kuma**, contingencia 4G/5G, 5 pruebas de aceptación (`PA-01` a `PA-05`) y riesgos. |
| **Andrés Garrido López** | Portavoz | Consultor Técnico y Presupuesto | Plano físico del local, inventario dimensionado, presupuesto Excel con IVA y guion del Pitch. |

---

## 📂 Estructura del Repositorio

```text
📦 nexus-arena-blueprint
 ┣ 📂 01_Documentacion
 ┃ ┣ 📜 Entrega 1 proyecto.pdf
 ┃ ┗ 📜 Entrega 2 proyecto.pdf
 ┣ 📂 02_Diagramas_y_Planos
 ┃ ┣ 📜 Plano Fisico NexusArena.png
 ┃ ┗ 📜 Topologia Logica VLANs.png
 ┣ 📂 03_Presupuesto_e_Inventario
 ┃ ┗ 📜 Presupuesto E2 NexusArena 2026.xlsx
 ┣ 📂 04_Prototipo_PacketTracer
 ┃ ┗ 📜 Prototipo Red NexusArena v1.pkt
 ┗ 📜 README.md
