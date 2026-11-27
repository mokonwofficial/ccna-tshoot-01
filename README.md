# AI-Solved CCNA v2.0 Labs — CML Lab Files

[日本語版 README はこちら (README_ja.md)](README_ja.md)

This repository provides the official Cisco Modeling Labs (CML) YAML topology files (55 hands-on troubleshooting labs: `Lab-01` – `Lab-55`) accompanying the book:

- **English Edition**: [*AI-Solved CCNA v2.0 Labs: 55 Hands-On Troubleshooting Scenarios Verified on Cisco Modeling Labs* (Amazon.com)](https://www.amazon.com/dp/B0HSSSTSJ2)
- **Japanese Edition**: 『AIが解く CCNA v2.0 Lab — TSHOOT編 実践55問 ー CMLで学ぶトラブルシューティング』 — [Amazon.co.jp (Kindle)](https://www.amazon.co.jp/dp/B0HSSQ5THM) / [BOOTH (PDF)](https://moko-nw.booth.pm/items/9228137)

## Reference Guides (`docs/`)

Before starting the labs, please refer to the following guides as needed:

- **[Lab Node Credentials (`docs/CREDENTIALS.md`)](docs/CREDENTIALS.md)**: Default Alpine Linux login (`cisco` / `cisco`) and lab-specific SSH / SFTP / SCP credentials.
- **[Post-Boot Manual Setup Guide (`docs/MANUAL_SETUP.md`)](docs/MANUAL_SETUP.md)**: One-time post-boot VLAN creation commands required for 6 labs due to CML IOL startup behavior.
- **[Errata & Notes (`docs/ERRATA.md`)](docs/ERRATA.md)**: Errata and notes regarding differences between the book listings and the CML lab files.

## Repository Structure

```text
ccna-tshoot-01/
├── README.md                    # English README (this file)
├── README_ja.md                 # Japanese README
├── docs/
│   ├── CREDENTIALS.md           # Lab node credentials (English)
│   ├── CREDENTIALS_ja.md        # Lab node credentials (Japanese)
│   ├── MANUAL_SETUP.md          # Post-boot manual setup guide (English)
│   ├── MANUAL_SETUP_ja.md       # Post-boot manual setup guide (Japanese)
│   ├── ERRATA.md                # Errata & notes (English)
│   └── ERRATA_ja.md             # Errata & notes (Japanese)
└── labs/
    ├── Lab-01.yaml
    ├── Lab-02.yaml
    ...
    └── Lab-55.yaml
```

## Tested Environment & Requirements

- **Platform**: Cisco Modeling Labs (CML) — compatible with **CML Free** (max 5 nodes per lab)
- **YAML Schema Version**: `0.3.1`
- **Node Definitions Used**: `alpine`, `iol-xe`, `ioll2-xe`, `iosvl2`, `unmanaged_switch`

## How to Import into CML

1. Download this repository as a ZIP file (`Code` -> `Download ZIP`) and extract it, or clone it via Git:
   ```bash
   git clone https://github.com/mokonwofficial/ccna-tshoot-01.git
   ```
2. Open your Cisco Modeling Labs (CML) Web UI.
3. Click **Import** on the Dashboard and select the desired YAML file (e.g., `labs/Lab-01.yaml`).
4. Open the imported lab, start all nodes, and begin troubleshooting by following the problem statement and constraints in the book.
   - *Note: Some labs require node credentials or a one-time post-boot VLAN command. Refer to the guides in `docs/` above.*

## Disclaimer & License Notice

- All lab topologies and configurations are provided for **educational and lab purposes only**. Do not apply them directly to production networks.
- Individual technical support for CML installation or lab setup is not provided.
- This is an independent publication and is not affiliated with, endorsed by, or sponsored by Cisco Systems, Inc. Cisco, CCNA, and Cisco Modeling Labs are trademarks or registered trademarks of Cisco Systems, Inc.
- Unauthorized redistribution or commercial reuse of these files is prohibited.

---

Author: **Moko Networks** ([@moko_nw](https://x.com/moko_nw))