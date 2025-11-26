# SCADA Attacks Lab

## Overview
This repository contains the implementation of a SCADA (Supervisory Control and Data Acquisition) security lab focusing on reconnaissance, MITM attacks, packet manipulation, and DoS techniques against a simulated industrial automation environment.

The lab includes:
- Siemens STEP7 PLC simulation  
- Wonderware InTouch HMI  
- NetToPLCSim PLC communication bridge  
- Kali Linux attacker VM with Ettercap + Wireshark  

The environment replicates a small industrial control network, allowing practical exploration of ICS‑specific threats.

---

## Experimental Setup

### Network Topology
- **Target1 – SCADA/HMI (Windows XP)**  
- **Target2 – PLC Simulation (Windows XP)**  
- **Attacker – Kali Linux 2024.x**

Subnet: **192.168.20.0/24**

---

## Lab Description & Objectives

This lab was designed to simulate and evaluate real-world cyberattacks targeting SCADA systems within a controlled industrial network environment. The objective was to understand how insecure configurations and unencrypted communications can be exploited by attackers using widely available tools.

### What was done:
- Built a virtual SCADA network with HMI and PLC simulation using **Wonderware InTouch**, **Siemens STEP7**, and **NetToPLCSim**
- Configured static IPs and verified communication between devices in the **192.168.20.0/24** subnet
- Used **Kali Linux** as the attacker machine to perform **ARP spoofing**, **DNS spoofing**, **packet injection**, and a basic **DoS attack**
- Captured and analyzed traffic using **Wireshark**
- Employed **Ettercap** to execute man-in-the-middle (MITM) attacks and inject custom filters to manipulate packets

### Tools Used:
- VirtualBox or VMware for virtualization
- **Kali Linux 2024.3** (Ettercap, Wireshark)
- **Windows XP SP3** (SCADA and PLC simulation)
- **NetToPLCSim** for bridging PLC data to the network
- **STEP7 v5.5** for PLC programming
- **Wonderware InTouch** for HMI interface

### Key Takeaways:
- **Unencrypted protocols (e.g., S7Comm) and flat networks** are extremely vulnerable to passive sniffing and MITM attacks.
- Ettercap filters allowed real-time manipulation of critical control signals (e.g., tank levels, valves).
- A simple DoS attack could bring the entire SCADA system to a halt, showing lack of redundancy and segmentation.

### Security Recommendations:
- **Network segmentation**: isolate control and corporate networks
- **Use of encrypted protocols** (e.g., S7Comm Plus or VPNs)
- **Intrusion Detection Systems (IDS)**: deploy tools like **Snort** or **Suricata** for real-time monitoring
- **Strict access control** and **MAC/IP filtering** on the switch level
- Periodic **security audits** and **penetration testing** of the ICS environment

---

## Descripción y Objetivos del Laboratorio

Este laboratorio fue diseñado para simular y evaluar ciberataques reales dirigidos a sistemas SCADA dentro de un entorno industrial controlado. El objetivo fue comprender cómo configuraciones inseguras y comunicaciones no cifradas pueden ser explotadas por atacantes usando herramientas ampliamente disponibles.

### Lo que se hizo:
- Se construyó una red SCADA virtual con simulación HMI y PLC usando **Wonderware InTouch**, **Siemens STEP7** y **NetToPLCSim**
- Se configuraron IPs estáticas y se verificó la comunicación entre dispositivos en la subred **192.168.20.0/24**
- Se usó **Kali Linux** como máquina atacante para realizar **ARP spoofing**, **DNS spoofing**, **inyección de paquetes** y un **ataque DoS básico**
- Se capturó y analizó tráfico con **Wireshark**
- Se usó **Ettercap** para ejecutar ataques de hombre-en-el-medio (MITM) e inyectar filtros personalizados

### Herramientas utilizadas:
- VirtualBox o VMware para la virtualización
- **Kali Linux 2024.3** (Ettercap, Wireshark)
- **Windows XP SP3** (simulación SCADA y PLC)
- **NetToPLCSim** para conectar los datos del PLC a la red
- **STEP7 v5.5** para programar el PLC
- **Wonderware InTouch** como interfaz HMI

### Conclusiones clave:
- **Protocolos sin cifrado (ej. S7Comm) y redes planas** son extremadamente vulnerables a sniffing pasivo y ataques MITM
- Los filtros de Ettercap permitieron manipular señales críticas de control en tiempo real (ej. niveles de tanques, válvulas)
- Un ataque DoS simple puede detener todo el sistema SCADA, demostrando la falta de segmentación y redundancia

### Recomendaciones de seguridad:
- **Segmentación de red**: separar las redes de control y corporativa
- **Uso de protocolos cifrados** (ej. S7Comm Plus o VPNs)
- Implementar **Sistemas de Detección de Intrusos (IDS)** como **Snort** o **Suricata**
- **Control de acceso estricto** y filtrado MAC/IP en switches
- Realizar **auditorías de seguridad** y **pruebas de penetración** periódicas en entornos ICS

---

## Описание лабораторной работы и цели

Эта лабораторная работа была разработана для моделирования и оценки реальных кибератак на SCADA-системы в контролируемой промышленной сети. Цель — понять, как уязвимые конфигурации и нешифрованные протоколы могут быть использованы злоумышленниками с помощью доступных инструментов.

### Что было сделано:
- Создана виртуальная SCADA-сеть с эмуляцией HMI и ПЛК, используя **Wonderware InTouch**, **Siemens STEP7** и **NetToPLCSim**
- Настроены статические IP-адреса и проверена связь между устройствами в подсети **192.168.20.0/24**
- Машина с **Kali Linux** использовалась для проведения **ARP-спуфинга**, **DNS-спуфинга**, **инъекций пакетов** и простой **DoS-атаки**
- Трафик захватывался и анализировался с помощью **Wireshark**
- **Ettercap** применялся для атак типа «человек посередине» (MITM) и внедрения кастомных фильтров

### Используемые инструменты:
- VirtualBox или VMware для виртуализации
- **Kali Linux 2024.3** (Ettercap, Wireshark)
- **Windows XP SP3** (SCADA и эмуляция ПЛК)
- **NetToPLCSim** для связи между ПЛК и сетью
- **STEP7 v5.5** для программирования ПЛК
- **Wonderware InTouch** для интерфейса HMI

### Основные выводы:
- **Нешифрованные протоколы (например, S7Comm)** и плоские сети легко поддаются пассивному перехвату и MITM-атакам
- С помощью Ettercap можно было в реальном времени изменять управляющие сигналы (например, уровни жидкости, клапаны)
- Простейшая DoS-атака может парализовать всю SCADA-систему, что указывает на отсутствие сегментации и резервирования

### Рекомендации по безопасности:
- **Сегментация сети**: разделить технологическую и корпоративную сети
- **Применение зашифрованных протоколов** (например, S7Comm Plus или VPN)
- Установка **систем обнаружения вторжений (IDS)**, таких как **Snort** или **Suricata**
- **Жёсткий контроль доступа** и фильтрация по MAC/IP на уровне коммутаторов
- Проведение **регулярных аудитов безопасности** и **пентестов** в ICS-среде

---

## Experimental Procedure

### Step 1 – Start STEP7 project
Launch the PLC logic using the file `Second(v.4_1)`.

![Checking_Work](screenshots/checking_work.jpg)

---

### Step 2 – Configure NetToPLCSim
Bridge PLC simulation to SCADA using IP **192.168.20.160**.

![NettoPLCsim](screenshots/nettoplcsim.jpg)

---

### Step 3 – Verify connectivity  
Ping the PLC simulation server from SCADA VM.

![Checking_ping](screenshots/check_ping.jpg)

---

### Step 4 – Check ARP table  
Confirm active hosts.

![ARP_TABLE](screenshots/arp_table.jpg)

---

### Step 5 – Configure SCADA VM network  
Assign static IP address.

![IP_CONFIG](screenshots/ip_address_config.jpg)

---

### Step 6 – Validate communication  
Ping between SCADA and PLC.

---

### Step 7 – Status of PLC variables  
![PARAMS](screenshots/params_status.jpg)

---

### Step 8 – Launch Wonderware InTouch  
![INTOUCH](screenshots/load_intouch.jpg)

---

### Step 9 – PLC/HMI runtime window  
![RUNTIME](screenshots/runtime.jpg)

---

# MITM Attacks (ARP Spoofing, DNS Spoofing, Packet Injection)

### Рисунок 11 – ARP table on SCADA during attack
![ARP_SCADA](screenshots/arp_table_intouch.jpg)

---

### Рисунок 12 – Configure IP on Kali  
![IP_KALI](screenshots/ip_address_kali.jpg)

---

### Рисунок 13 – Connectivity test to both targets  
![TARGET](screenshots/ping_kali.jpg)

---

### Рисунок 14 – Start Ettercap and select interface  
![ETTERCAP](screenshots/start_ettercap.jpg)

---

### Рисунок 15 – Host scan  
![HOST_SCAN](screenshots/scan_port.jpg)

---

### Рисунок 16 – Host list  
![HOST_LIST](screenshots/list_port.jpg)

---

### Рисунок 17 – Add hosts to Target1/Target2  
![HOST_TARGET](screenshots/host_target_list.jpg)

---

### Рисунок 18 – Protocol setup for packet filtering  
![WIRE](screenshots/setting_wireshark.jpg)

---

### Рисунок 19 – ARP poisoning attack  
![ARP_POISONING](screenshots/arp_poisoning.jpg)

---

# Packet Capture & Manipulation (Wireshark + Ettercap)

### Рисунок 21 – Capturing packets after MITM begins
![PACKETS_ARP](screenshots/packets_arp_poisoning.jpg)

---

### Рисунок 22 – Enabling Ettercap plugin `dns_spoof`
![PLUGGING](screenshots/pluggin_dns_spoof.jpg)

---

### Рисунок 23 – Loading custom attack script  
![FILTER](screenshots/applied_filter.jpg)

---

### Рисунок 24 – Finding a packet with value `00 55`
![PACKET_FIND](screenshots/packet_cero_five.jpg)

---

### Filter applied successfully  

---

# DoS Attack & Final Result

### Рисунок 26 – Executing DoS attack  
![DOS_SENT](screenshots/dos_attack_sent.jpg)

---

### Рисунок 27 – Packets captured during DoS  
![WIRE_SENT](screenshots/wireshark_dos_attack.jpg)

---

### Рисунок 28 – DoS attack successful  
![WM_ATTACK](screenshots/vm_dos_attack_successful.jpg)

---

# Author
**Bruno P. Huaman Vela**  
Information Security in Telecommunication Systems  
Ural Federal University – 2025



