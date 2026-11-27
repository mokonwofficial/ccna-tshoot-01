# Post-Boot Manual Setup Guide

This document lists lab-internal configurations that cannot be applied automatically from the YAML initial configuration due to CML (Cisco Modeling Labs) IOL / Alpine Linux image behavior, along with the commands to run manually before starting the exercises.

---

## 1. Labs Requiring Post-Boot VLAN Creation (Required / Recommended)

The CML IOL L2 image (`ioll2-xe`) does not automatically apply `vlan <ID>` commands from the startup configuration to the VLAN database (only VLANs assigned to access ports are created automatically).

For the following 6 labs, log in to the listed switches after the lab boots and run the VLAN creation command once before starting the exercise:

| Lab | Switch(es) | Missing VLAN(s) | Command |
| :--- | :--- | :--- | :--- |
| **Lab-08** | SW1, SW2 | VLAN 99 | `vlan 99` |
| **Lab-09** | SW1, SW2 | VLAN 10, 20 | `vlan 10` and `vlan 20` |
| **Lab-14** | SW1, SW2, SW3 | VLAN 10 | `vlan 10` |
| **Lab-15** | SW3 | VLAN 10 | `vlan 10` |
| **Lab-17** | SW2 | VLAN 10 | `vlan 10` |
| **Lab-18** | SW1, SW2, SW3 | VLAN 10 | `vlan 10` |

### Example (on each affected switch)

```text
configure terminal
vlan 10
end
```

- *Note: Do not modify trunk encapsulation, native VLAN, allowed VLAN lists, or existing access-port assignments.*
- *Note: Lab-11, Lab-19, and Lab-50 through Lab-53 automatically create the required VLANs via access-port assignments, so no manual action is needed.*

---

## 2. Optional Manual Settings (No Impact on Exercise Functionality)

The following two items do not affect connectivity or troubleshooting outcomes. Perform them only if you want the lab state to match the book's configuration listings verbatim.

### VLAN Name `USERS` (Lab-14 / Lab-53)
Due to IOL startup behavior, the VLAN name (`name USERS`) is not applied on boot and defaults to `VLAN0010`. If you wish to set the name, run the following on the relevant switch (for Lab-14, combine this with step 1 above; for Lab-53, VLAN 10 is already created automatically):

```text
configure terminal
vlan 10
name USERS
end
```

### File Ownership on Lab-44 PC1
The YAML initial configuration automatically creates `/home/cisco/test.txt` with the content `Lab-044 SCP test`, but CML's Alpine initialization creates it with `root:root` ownership (mode `644`). The file is readable by the `cisco` user and does not affect the SCP exercise. If you wish to change the ownership to `cisco:cisco`, log in to PC1 as `cisco` and run:

```sh
sudo chown cisco:cisco /home/cisco/test.txt
```