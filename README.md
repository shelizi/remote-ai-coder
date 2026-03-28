# Remote AI Coder

Remote AI Coder is a VS Code extension paired with a PWA Web UI that lets you securely operate local AI CLI tools (e.g., `codex`, `claude`, `aider`) from any browser, review terminal output, and send commands in real time.

## Value Proposition

- **Remote control on any device** – Launch a controlled HTTP/WebSocket service from VS Code so phones, tablets, or laptops can take over the terminal session instantly.
- **Layered security** – PIN/password plus JWT, along with folder access modes (`workspaceOnly`, `whitelist`) to minimize accidental misuse.
- **Rich CLI orchestration** – Auto-detect installed AI CLIs and spin up multiple PTY sessions, each with independent lifecycle management.
- **Intelligent Git panel** – Inspect repo status, preview diffs, switch branches, and request AI-generated commit messages or branch names from the browser.
- **Ephemeral task mode** – Run sensitive jobs through dedicated providers that leave no session or command history once finished.
- **Full localization coverage** – Uses VS Code’s native l10n pipeline to offer Traditional/Simplified Chinese, English, Japanese, Korean, and multiple European languages.

## Key Capabilities

| Capability | Description |
| --- | --- |
| Multi-CLI auto detection | Scans PATH/HTTP targets for `claude`, `cursor`, `opencode`, `aider`, `codex`, `copilot`, `kimi`, `gemini`, `qwen`, and more. |
| Session management | Create, switch, stop, and reconnect multiple PTY sessions with idle auto-cleanup. |
| Git control | View staged/unstaged/untracked files, inspect diffs, change branches, and perform common graph operations. |
| AI helpers | `AI Generate` (commit message suggestions) and `AI Branch` (branch name ideas) powered by pluggable Ephemeral CLI providers. |
| Quick Commands | Save frequently used commands and trigger them in the Web UI. |
| Mobile-friendly input | On-screen Tab, Esc, arrow keys, and other shortcuts for touchscreen workflows. |
| Public tunnel options | Provision Dev Tunnel (with cloudflared fallback when required). |

## Supported CLIs

Current detection matrix:

```
claude, cursor, opencode, aider, codex, copilot, kimi, gemini, qwen
```

Need another CLI prioritized? File an issue so we can adjust the roadmap.

## CLI Support Status

| CLI | Status | AI Git Helpers |
| --- | --- | --- |
| Codex | ✅ Fully tested | ✅ Commit & Branch |
| Copilot | 🧪 Experimental | 🚧 In development |
| Claude | 🧪 Experimental | 🚧 In development |
| Cursor | 🧪 Experimental | 🚧 In development |
| OpenCode | 🧪 Experimental | ✅ Commit & Branch |
| Aider | 🧪 Experimental | 🚧 In development |
| Kimi | 🧪 Experimental | 🚧 In development |
| Gemini | 🧪 Experimental | 🚧 In development |
| Qwen | 🧪 Experimental | 🚧 In development |

## Localization

- Built-in languages: zh-TW, zh-CN, en, ja, ko, es, fr, de, pt, it, ar.

## Security Guidance

1. Prefer `workspaceOnly` or `whitelist` access modes.
2. Use strong, unique passwords.
3. If a public tunnel is open, monitor session status and expiry regularly.
4. Adjust `remoteAiCoder.port` in the settings panel when encountering port conflicts.

## Third-Party Software Disclaimer

This extension may download third-party executables **only with your explicit consent**. Before any download begins, a confirmation dialog explains what will be downloaded, from where, and links to official documentation.

| Software | Provider | License / Terms | Documentation |
| --- | --- | --- | --- |
| Dev Tunnels CLI | Microsoft | [Microsoft Software License Terms](https://aka.ms/devtunnels/tos) | [Dev Tunnels docs](https://learn.microsoft.com/azure/developer/dev-tunnels/) |
| cloudflared | Cloudflare | [Apache 2.0](https://github.com/cloudflare/cloudflared/blob/master/LICENSE) | [Cloudflare Tunnel docs](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/) |

**Remote AI Coder does not develop, maintain, audit, or endorse these programs.** They are subject to their own license terms. You use them at your own risk. See the [`LICENSE`](LICENSE) file, Section 7, for detailed legal terms.

## Support & Roadmap

- Expanding Ephemeral providers to cover additional AI CLIs.
- Enhancing Git workflows, mobile input ergonomics, and Quick Commands.
- We welcome bug reports and feature suggestions to help focus upcoming releases.

## License

**Remote AI Coder Proprietary License v1.0** (see [`LICENSE`](LICENSE), dated 2026‑03‑01).

- ✅ Permitted: personal/non-commercial use and internal enterprise use.
- ✅ Output ownership: everything produced through the software belongs to you.
- ❌ Prohibited: modifying/deriving, reverse engineering, redistribution, or offering hosted/SaaS services without approval.
- ⚠️ Termination: rights end automatically upon breach; all copies must be destroyed.
- ⚖️ Liability: provided “as is,” without warranties; governed by the laws of Taiwan (R.O.C.).
## Disclaimer

Remote AI Coder enables **remote access to local development environments** and **AI-powered CLI tools**. By using this software, you acknowledge and accept that:

- The author is **not liable** for any data loss, security breaches, unauthorized access, or damages of any kind arising from the use of this software.
- AI CLI tools may produce **unintended, erroneous, or destructive outputs**. You are solely responsible for reviewing and approving all actions performed through terminal sessions.
- Public tunnel connections expose local services to the internet. You are responsible for configuring strong passwords, appropriate access modes, and monitoring active sessions.
- This software is provided **"as is"** with no guarantees of security, availability, or fitness for any purpose.

See the [`LICENSE`](LICENSE) file, Section 5, for full legal terms.
---

Need another language version? Let us know and we can adapt this public-facing README.
