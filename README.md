# NEXUS ARENA (Entrega 2)

> Proyecto Intermodular · 2.º SMR · DAVANTE MEDAC JAÉN · Curso 2026/27  
> **Equipo 2** · Fecha límite de entrega: 27/11/2026

Repositorio oficial de diseño técnico, presupuesto, planos y prototipado de red para **NEXUS ARENA**, un centro de eSports y streaming con 12 puestos gaming, 2 boxes de streaming, recepción y zona de espectadores.

---

## Resumen Ejecutivo del Proyecto

| Parámetro | Especificación del Diseño |
| :--- | :--- |
| **Cliente** | NEXUS ARENA — Centro de eSports y Streaming |
| **Alternativa Elegida** | **Alternativa 2:** Segmentación por VLANs + Servidor Virtualizado + Enlace de respaldo 4G/5G |
| **Presupuesto Máximo** | 18.000,00 €  |
| **Presupuesto Cerrado** | 13.760,00 € (Base Imponible) · IVA 21 %: 2.889,60 € · Total con IVA: 16.649,60 € |
| **Costes Periódicos** | 75,00 € / mes |
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
## 🌐 Arquitectura de Red (Segmentación Lógica)

Para cumplir con la QoS exigida por los streamers y las normativas de seguridad, el entorno se ha segmentado de la siguiente manera (comprobable en el archivo `.pkt` de la carpeta `04_Prototipo_PacketTracer`):

| VLAN | Nombre | Subred | Propósito | 
| ----- | ----- | ----- | ----- | 
| **VLAN 10** | GAMING | `192.168.10.0/24` | Tráfico exclusivo y de baja latencia para los 12 PCs de juego. | 
| **VLAN 20** | STREAMING | `192.168.20.0/24` | Puestos de retransmisión. Prioridad máxima de ancho de banda. | 
| **VLAN 30** | STAFF | `192.168.30.0/24` | Gestión, recepción y administración del negocio. | 
| **VLAN 40** | INVITADOS | `192.168.40.0/24` | Acceso Wi-Fi público **(Aislado de la red local)**. | 
| **VLAN 50** | SERVIDORES | `192.168.50.0/24` | Entorno Proxmox, NAS (Nextcloud) y Uptime Kuma. | 

## 🛡️ Seguridad y Verificación de la Condición de Éxito

En el prototipo de Packet Tracer se ha implementado una **Access Control List (ACL)** denominada `REGLAS_NEXUS` en la interfaz del router que gestiona a los invitados (`GigabitEthernet0/0.40`). 

Esta lista bloquea explícitamente cualquier petición desde la red Wi-Fi de Invitados (VLAN 40) hacia los Servidores (VLAN 50) o los ordenadores de producción (VLAN 10, 20 y 30), previniendo posibles ataques, robos de datos o saturación intencionada de la red LAN.
