# Remote AI Coder

Remote AI Coder 是一套結合 VS Code 擴充與 PWA Web UI 的遠端操作解決方案，讓你能在任何瀏覽器安全操控本機 AI CLI 工具（如 `codex`、`claude`、`aider`），同步查看終端輸出並即時輸入指令。

## 主要價值

- **跨裝置遠端操作**：在 VS Code 啟動受控 HTTP/WebSocket 服務，手機、平板或筆電都能即時接手終端畫面與輸入。
- **多層安全機制**：提供 密碼 + JWT，以及 `workspaceOnly`、`whitelist` 三種資料夾存取模式，降低誤用風險。
- **多 CLI 管理**：自動偵測已安裝的 AI CLI，支援多個 PTY session 的建立、切換、停止與閒置回收。
- **智慧 Git 面板**：直接在 Web UI 檢視狀態、預覽 diff、切換分支，並透過 AI 取得 commit 與 branch 建議。
- **完整在地化**：採 VS Code 原生 l10n 機制，支援繁中、簡中、英文、日文、韓文與多種歐洲語言。

## 主要功能

| 功能 | 說明 |
| --- | --- |
| 多 CLI 自動偵測 | 掃描 PATH/HTTP 來源，支援 `claude`, `cursor`, `opencode`, `aider`, `codex`, `copilot`, `kimi`, `gemini`, `qwen` 等工具。|
| Session 管理 | 建立/切換/停止/重連多個 PTY session，並提供閒置自動清除。|
| Git 控制 | 檢視 staged/unstaged/untracked、檔案 diff、分支切換與常用節點操作。|
| AI 助理 | `AI Generate`（commit 建議）與 `AI Branch`（branch 建議），透過可擴充的 Ephemeral CLI provider 提供。|
| Quick Commands | 自訂常用指令並在 Web UI 快速呼叫。|
| 行動輸入優化 | 內建 Tab、Esc、方向鍵等虛擬按鍵，適合觸控使用。|
| 公開 Tunnel | 可啟用 Dev Tunnel（必要時 fallback cloudflared），供外部裝置連線。|

## 支援 CLI 清單

目前可偵測並整合：

```
claude, cursor, opencode, aider, codex, copilot, kimi, gemini, qwen
```

若你需要其他 CLI 優先支援，歡迎透過 issue 提出，我們會納入 Roadmap。

## CLI 支援狀況

| CLI | 狀態 | AI Git 助理 |
| --- | --- | --- |
| Codex | ✅ 完整測試 | ✅ Commit & Branch |
| Copilot | 🧪 實驗階段 | 🚧 開發中 |
| Claude | 🧪 實驗階段 | 🚧 開發中 |
| Cursor | 🧪 實驗階段 | 🚧 開發中 |
| OpenCode | 🧪 實驗階段 | ✅ Commit & Branch |
| Aider | 🧪 實驗階段 | 🚧 開發中 |
| Kimi | 🧪 實驗階段 | 🚧 開發中 |
| Gemini | 🧪 實驗階段 | 🚧 開發中 |
| Qwen | 🧪 實驗階段 | 🚧 開發中 |

## 語系與在地化

- 內建語言：繁中、簡中、英文、日文、韓文、西班牙文、法文、德文、葡萄牙文、義大利文、阿拉伯文。

## 安全建議

1. 優先使用 `workspaceOnly` 或 `whitelist`。
2. 請設定強密碼。
3. 若開啟公開 tunnel，記得定期檢查連線狀態與有效期限。
4. 若遇到 Port 衝突，可在設定面板調整 `remoteAiCoder.port`。

## 第三方軟體免責聲明

本擴充可能會下載第三方執行檔，**僅在您明確同意後執行**。在任何下載開始前，系統會顯示確認對話方塊，說明將下載的內容、來源，並提供官方文件連結。

| 軟體 | 提供者 | 授權條款 | 文件 |
| --- | --- | --- | --- |
| Dev Tunnels CLI | Microsoft | [Microsoft 軟體授權條款](https://aka.ms/devtunnels/tos) | [Dev Tunnels 文件](https://learn.microsoft.com/azure/developer/dev-tunnels/) |
| cloudflared | Cloudflare | [Apache 2.0](https://github.com/cloudflare/cloudflared/blob/master/LICENSE) | [Cloudflare Tunnel 文件](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/) |

**Remote AI Coder 不負責開發、維護、審查或背書上述程式。**各程式適用其各自的授權條款，使用風險由您自行承擔。詳細法律條款請參見 [`LICENSE`](LICENSE) 檔案第 7 條。

## 支援與規劃

- 逐步擴展 Ephemeral provider，支援更多第三方 AI CLI。
- 優化 Git 工作流程、行動端輸入體驗與 Quick Commands。
- 歡迎提交錯誤回報或功能建議，協助我們調整優先順序。

## 授權

**Remote AI Coder 專有授權 v1.0**（詳見 [`LICENSE`](LICENSE)，發布日期 2026-03-01）。

- ✅ 允許：個人/非商業使用與企業內部使用。
- ✅ 產出：使用者透過本軟體產出的結果完全歸屬於使用者。
- ❌ 禁止：修改、衍生、反編譯、散布，或未經許可提供商業託管/SaaS 服務。
- ⚠️ 終止：違反授權會自動終止，需停止使用並銷毀所有副本。
- ⚖️ 法律：軟體依「現狀」提供，不附保固；授權受中華民國法律管轄。

## 免責聲明

Remote AI Coder 提供**遠端存取本機開發環境**與**AI 命令列工具操控**功能。使用本軟體即表示您知悉並同意：

- 作者**不對**因使用本軟體所造成的任何資料遺失、安全漏洞、未經授權存取或任何形式的損害負責。
- AI CLI 工具可能產生**非預期、錯誤或具破壞性的輸出**。您有責任自行審查並確認所有透過終端機執行的操作。
- 公開通道連線會將本機服務暴露至網際網路。您有責任設定強密碼、適當的存取模式，並監控使用中的連線。
- 本軟體依**「現狀」**提供，不保證安全性、可用性或適用於任何特定用途。

完整法律條款請參見 [`LICENSE`](LICENSE) 檔案第 5 條。

---

若需要其他語言版本，我們可在此公開版 README 基礎上協助客製。
