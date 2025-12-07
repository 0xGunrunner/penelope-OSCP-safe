# PenelopeOSCPSafe

This is an OSCP+-safe fork of [Penelope](https://github.com/brightio/penelope), a powerful shell handler and modern netcat replacement for RCE exploitation. It simplifies post-exploitation while removing features that could violate OSCP+ rules: Meterpreter integration, `upload_privesc_scripts` (automated privesc helpers), and `peass_ng` (AI-enhanced enumeration).

## OSCP+ Exam Disclaimer
Modified for OSCP+ compliance by removing auto-exploitation, AI usage, and restricted Metasploit features. Auto-enumeration is retained as permitted. Use manually and verify with Offensive Security rules.

## Install
Install via pipx from GitHub:

```bash
pipx install git+https://github.com/0xGunrunner/penelopeoscpsafe.git
```

## Features
### Session Features
- Auto-upgrade to PTY (Unix) or readline (Windows)
- Real-time terminal resize (Unix)
- Logging, file upload/download, in-memory script execution
- Local port forwarding, multi-tab shells, auto-respawn

### Global Features
- Multi-session/listener management
- Streamlined modules (enumeration-focused, no auto-privesc/AI)
- HTTP file serving
- Importable for exploits

### Modules
Limited to OSCP-safe: enumeration (e.g., lse, linuxexploitsuggester), persistence, pivoting, forensics. See script for full list.

## Usage
Run with:

```bash
penelope-OSCP-safe [arguments]
```

Examples:
- `penelope-OSCP-safe` : Listen for reverse shells on 0.0.0.0:4444
- `penelope-OSCP-safe -p 5555` : Listen on port 5555
- `penelope-OSCP-safe -c target -p 3333` : Connect to bind shell
- `penelope-OSCP-safe ssh user@target` : Reverse shell via SSH
- `penelope-OSCP-safe -s <File/Folder>` : HTTP serve file/folder

Main menu: Use F12/Ctrl+C to detach shell. Supports TAB completion.

For full options: `penelopeOSCPsafe -h`

## FAQ
### Is this allowed in OSCP+?
Yes, with removed modules. Avoid automation that violates rules.

### How to detach shell?
PTY: F12; Raw: Ctrl+C. Shown on attach.

### Contribute?
Report bugs or ideas via issues/PRs.

Original credits: Thanks to early contributors from Penelope.
