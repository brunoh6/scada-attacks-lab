# SCADA Attacks Lab

## Overview
This repository contains the implementation of a lab exercise focused on the exploitation and analysis of vulnerabilities in SCADA (Supervisory Control and Data Acquisition) systems. The simulation involves virtual machines running Windows XP with industrial control software, such as Siemens STEP7 and Wonderware InTouch, emulating a basic industrial automation environment. The attacker machine (Kali Linux) performs scanning, ARP spoofing, DNS spoofing, and packet injection.

---

## Experimental Setup

### Network Topology
- **Target1 (SCADA VM)**: Hosts InTouch Runtime and HMI.
- **Target2 (PLC Simulation)**: Runs Siemens STEP7 and NetToPLCSim to simulate PLC behavior.
- **Attacker (Kali Linux)**: Used for reconnaissance and attacks.

All machines are on the same subnet (192.168.20.0/24).

---

## Experimental Procedure

### Step 1 – Start STEP7 project
The lab begins by launching the STEP7 project file `Second(v.4_1)` which contains logic for simulating PLC processes.

**🖼️ Screenshot:** `checking_work.jpg`

---

### Step 2 – Configure NetToPLCSim
The server is set up using `NetToPLCSim` and bound to IP `192.168.20.160`, acting as a bridge between the SCADA interface and the simulated PLC.

**🖼️ Screenshot:** `nettoplcsim.jpg`

---

### Step 3 – Check server connection
The correct functioning is verified by pinging the configured IP.

**🖼️ Screenshot:** `check_ping.jpg`

---

### Step 4 – View ARP table
Confirm the devices detected on the network.

**🖼️ Screenshot:** `arp_table.jpg`

---

### Step 5 – IP configuration of SCADA VM
SCADA VM is assigned a static IP (e.g., `192.168.20.130`) to ensure consistent communication.

**🖼️ Screenshot:** `ip_address_config.jpg`

---

### Step 6 – Ping test between VMs
Verify bidirectional connectivity between SCADA and PLC simulation.

**🖼️ Screenshot:** `check_ping.jpg` (already referenced)

---

### Step 7 – View parameter status
Confirm system values (levels, temperatures, valve status, etc.)

**🖼️ Screenshot:** `params_status.jpg`

---

### Step 8 – Launch InTouch HMI
The InTouch interface is started to display a simulated HMI (Human-Machine Interface).

**🖼️ Screenshot:** `load_intouch.jpg`

---

### Step 9 – HMI main window
Displays the full process simulation: reservoirs, valves, compressor, emergency stop, etc.

**🖼️ Screenshot:** `378FD61D-A390-41F0-ACE2-D7D36A2BB074.png`

---

## Next Steps
- Add ARP spoofing, DNS spoofing, and packet injection documentation
- Add Ettercap filter setup
- Add DoS attack execution
- Include PCAP analysis and potential countermeasures

## Author
Bruno P. Huaman Vela  
Student of Information Security in Telecommunication Systems  
UrFU, 2025
