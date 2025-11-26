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


