# Lab Node Credentials

This file lists **lab-internal network device and host (Alpine Linux) credentials only**. These passwords are intentionally simple for training purposes and must never be reused in production or other environments.

## Alpine Linux Nodes (Default for All Labs)

| Username | Password | Notes |
| :--- | :--- | :--- |
| `cisco` | `cisco` | Default login for Alpine Linux nodes (PC1, PC2, SRV1, etc.) |

## Lab-Specific Credentials

| Lab | Node | Username | Password | Used For |
| :--- | :--- | :--- | :--- | :--- |
| Lab-42 | R1 | `admin` | `Cisco123` | SSH login from R2 (VTY local authentication) |
| Lab-43 | SRV1 | `backup` | `Cisco123` | SFTP / SSH server on SRV1 |
| Lab-44 | R1 | `scpadmin` | `Cisco123` | SSH login and SCP transfer from PC1 |
| Lab-44 | PC1 | `cisco` | `cisco` | Alpine Linux login / SCP client |
| Lab-49 | R3 | `admin` | `cisco123` | SSH login from R1 (ACL 110 permits TCP/22) |

## Notes

- **Lab-42 R2** and **Lab-49 R1 / R2** act as SSH clients and have no local login accounts configured for these exercises.
- In **Lab-43**, R1 is the SFTP client and SRV1 is the SFTP server.
- On **Lab-44 PC1**, `/home/cisco/test.txt` is created with `root:root` ownership (mode `644`) due to CML's Alpine initialization behavior. It is readable by the `cisco` user and does not affect the SCP exercise (see [MANUAL_SETUP.md](MANUAL_SETUP.md) if you wish to change its ownership).
- Console access to lab nodes does not require the credentials above unless console authentication is explicitly enabled in the device configuration.