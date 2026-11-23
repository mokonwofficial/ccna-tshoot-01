# AIが解く CCNA v2.0 Lab（TSHOOT編 実践55問）— CML ラボファイル

[English README is available here (README.md)](README.md)

本リポジトリは、以下の書籍に対応する Cisco Modeling Labs (CML) 用の初期トポロジ YAML ファイル（全55問：`Lab-01` 〜 `Lab-55`）を公開する公式リポジトリです。

- **日本語版**：『AIが解く CCNA v2.0 Lab — TSHOOT編 実践55問 ー CMLで学ぶトラブルシューティング』
- **英語版**：*AI-Solved CCNA v2.0 Labs: 55 Hands-On Troubleshooting Scenarios Verified on Cisco Modeling Labs*

## ディレクトリ構成

```text
ccna-tshoot-01/
├── README.md        # 英語版 README
├── README_ja.md     # 日本語版 README（本ファイル）
└── labs/
    ├── Lab-01.yaml
    ├── Lab-02.yaml
    ...
    └── Lab-55.yaml
```

## 検証環境・動作要件

- **検証基盤**：Cisco Modeling Labs (CML) — **CML Free 対応**（1ラボあたり最大 5 ノード）
- **YAML スキーマバージョン**：`0.3.1`
- **使用ノード定義**：`alpine`, `iol-xe`, `ioll2-xe`, `iosvl2`, `unmanaged_switch`

## CML へのインポート手順

1. 右上の `Code` → `Download ZIP` から一括ダウンロードして解凍するか、以下のコマンドでクローンします。
   ```bash
   git clone https://github.com/mokonwofficial/ccna-tshoot-01.git
   ```
2. Cisco Modeling Labs (CML) の Web UI にログインします。
3. ダッシュボード右上の **Import** をクリックし、演習したいラボの YAML ファイル（例：`labs/Lab-01.yaml`）を選択します。
4. インポートされたラボを開き、全ノードを起動したうえで、書籍の問題文・制約事項に沿ってトラブルシューティングを進めてください。

## 免責事項・ご注意

- 本リポジトリのファイルは学習および仮想ラボ環境での検証目的でのみ提供されています。本番稼働環境への直接適用は行わないでください。
- CML の環境構築手順や演習環境に関する個別の技術サポートは行っておりません。
- 本書および本リポジトリは著者の独立した制作物であり、Cisco Systems, Inc. と提携・承認・後援されたものではありません。Cisco、CCNA、Cisco Modeling Labs は Cisco Systems, Inc. の商標または登録商標です。
- 本リポジトリ内ファイルの無断転載・再配布・商用二次利用は禁止します。

---

著者：**もー子** ([@moko_nw](https://x.com/moko_nw))
