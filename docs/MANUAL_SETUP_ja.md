# ラボ起動後の手動設定ガイド

本ファイルでは、CML（Cisco Modeling Labs）の IOL / Alpine Linux イメージの仕様により、YAML の初期コンフィグから自動反映できない設定と、演習前に手動で投入するコマンドをまとめています。

---

## 1. 起動後に VLAN 作成が必要なラボ（必須・推奨）

CML の IOL L2 イメージ（`ioll2-xe`）は、起動時コンフィグ（startup-config）に記載された `vlan <ID>` コマンドを VLAN データベースへ自動反映しない仕様があります（アクセスポートに割り当てられた VLAN のみ自動作成されます）。

そのため、以下の 6 ラボでは、ラボ起動後に該当スイッチへログインし、演習開始前に 1 回だけ VLAN 作成コマンドを投入してください。

| ラボ | 対象スイッチ | 未作成の VLAN | 投入コマンド |
| :--- | :--- | :--- | :--- |
| **Lab-08** | SW1, SW2 | VLAN 99 | `vlan 99` |
| **Lab-09** | SW1, SW2 | VLAN 10, 20 | `vlan 10` および `vlan 20` |
| **Lab-14** | SW1, SW2, SW3 | VLAN 10 | `vlan 10` |
| **Lab-15** | SW3 | VLAN 10 | `vlan 10` |
| **Lab-17** | SW2 | VLAN 10 | `vlan 10` |
| **Lab-18** | SW1, SW2, SW3 | VLAN 10 | `vlan 10` |

### 投入例（対象スイッチごと）

```text
configure terminal
vlan 10
end
```

- ※ トランクのカプセル化、ネイティブ VLAN、許可 VLAN リスト、および既存のアクセスポート設定は変更しないでください。
- ※ Lab-11、Lab-19、Lab-50〜53 はアクセスポート割り当てにより必要な VLAN が自動作成されるため、手動対応は不要です。

---

## 2. 任意の手動設定（演習の動作には影響なし）

以下の 2 点は演習の成否や通信自体には影響しませんが、書籍の記載と完全に状態を揃えたい場合のみ実施してください。

### VLAN 名 `USERS` の設定（Lab-14 / Lab-53）
IOL の起動仕様により、VLAN 名（`name USERS`）は初期反映されず既定名（`VLAN0010`）になります。名前を揃えたい場合は、該当スイッチ（Lab-14 は上記 1 の作業とあわせて実施、Lab-53 は VLAN 10 自体は自動作成済み）で以下を実行してください。

```text
configure terminal
vlan 10
name USERS
end
```

### Lab-44 PC1 のテストファイル所有者変更
YAML の初期設定により `/home/cisco/test.txt`（内容：`Lab-044 SCP test`）は自動生成されますが、CML の Alpine 初期化仕様により所有者が `root:root`（権限 `644`）となります。`cisco` ユーザーから読み取り可能であり SCP 演習に支障はありませんが、所有者を `cisco:cisco` へ揃えたい場合は PC1 に `cisco` でログイン後、以下を実行してください。

```sh
sudo chown cisco:cisco /home/cisco/test.txt
```