# AI-Solved CCNA v2.0 Labs — CML Lab Files

[日本語版 README はこちら (README_ja.md)](README_ja.md)

This repository provides the official Cisco Modeling Labs (CML) YAML topology files (55 hands-on troubleshooting labs: `Lab-01` – `Lab-55`) accompanying the book:

- **English Edition**: [*AI-Solved CCNA v2.0 Labs: 55 Hands-On Troubleshooting Scenarios Verified on Cisco Modeling Labs* (Amazon.com)](https://www.amazon.com/dp/B0HSSSTSJ2)
- **Japanese Edition**: [『AIが解く CCNA v2.0 Lab — TSHOOT編 実践55問 ー CMLで学ぶトラブルシューティング』 (Amazon.co.jp)](https://www.amazon.co.jp/dp/B0HSSQ5THM)

## Repository Structure

```text
ccna-tshoot-01/
├── README.md        # English README (this file)
├── README_ja.md     # Japanese README
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

## Disclaimer & License Notice

- All lab topologies and configurations are provided for **educational and lab purposes only**. Do not apply them directly to production networks.
- Individual technical support for CML installation or lab setup is not provided.
- This is an independent publication and is not affiliated with, endorsed by, or sponsored by Cisco Systems, Inc. Cisco, CCNA, and Cisco Modeling Labs are trademarks or registered trademarks of Cisco Systems, Inc.
- Unauthorized redistribution or commercial reuse of these files is prohibited.

---

Author: **Moko Networks** ([@moko_nw](https://x.com/moko_nw))