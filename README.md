# MCP Server Configs for Tricentis Tools

This repository contains ready-to-use `mcp.json` files for connecting Tricentis tools (Tosca Cloud, qTest, NeoLoad) to AI-powered IDEs like **VS Code**, **Cursor**, and **Visual Studio**.

## 🧰 Tools Supported

- ✅ Tricentis Tosca Cloud
- ✅ Tricentis qTest
- ✅ Tricentis NeoLoad

## 💻 IDEs Supported

- VS Code
- Cursor
- Visual Studio

---

## 🔧 Setup Instructions

### 1. Install Node.js (latest LTS)

- Download: https://nodejs.org

### 2. Prerequisites

- Access to your Tricentis tenant (Tosca, qTest, or NeoLoad)
- For qTest: API Token with MCP permissions
- Port `56874` must be available (Tosca/NeoLoad requirement)

---

## 📂 MCP JSON Files

| Tool        | IDE           | File                                   |
|-------------|---------------|----------------------------------------|
| Tosca Cloud | VS Code       | `tosca.vscode.mcp.json`                |
| Tosca Cloud | Cursor        | `tosca.cursor.mcp.json`                |
| Tosca Cloud | Visual Studio | `tosca.visualstudio.mcp.json`         |
| qTest       | Cursor        | `qtest.cursor.mcp.json`                |
| NeoLoad     | VS Code       | `neoload.vscode.mcp.json`              |

Place the appropriate file in your workspace root or IDE-specific settings directory.

---

## 🚀 IDE Setup

### VS Code
1. Place the `.mcp.json` file in the root of your project.
2. Add to `.vscode/settings.json`:
   ```json
   {
     "chat.mcp.enabled": true,
     "mcp": {
       "servers": "./<filename>.json"
     }
   }
   ```

### Cursor IDE
1. Open Cursor → Settings → MCP Tools.
2. Click "Add MCP Server".
3. Paste contents of the appropriate JSON file.
4. Save and restart.

### Visual Studio
1. Use an extension that supports `mcp.json`.
2. Load the correct file into the extension’s config directory.

---

## 🔐 qTest API Token Setup

For `qtest.cursor.mcp.json`:

1. Replace the placeholder:
   ```json
   "QTEST_TOKEN": "<your‑qTest‑API‑token>"
   ```
2. Generate token from your qTest profile or admin panel.

---

## ✅ Test Connectivity

Use prompts in your IDE:
- `List all Tosca test cases`
- `Fetch defects from qTest`
- `Show NeoLoad scenarios`

You should see successful responses once connected.

---

## 🧪 Troubleshooting

- Ensure your tenant URL is correct (e.g., `yourtenant.my.tricentis.com`)
- Make sure port `56874` is open
- For qTest, verify the token has proper permissions
- Use `npx mcp-remote@latest` manually to test commands

---

## 📝 License

[MIT License](LICENSE)

---

Made with ❤️ by [Gio](https://github.com/fillegar)
