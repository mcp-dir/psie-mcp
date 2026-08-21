# Consulta de Radar (PSIE/Inmetro)

### Consulta de Radar (PSIE/Inmetro) for Claude, ChatGPT and AI agents

Look up the metrological status of a city's speed cameras and breathalyzers in Inmetro's official records (PSIE), the same data a citizen accesses: serial number, direction, nominal speed, operator, location, validity date and verification result (approved, failed or repaired). Useful to check whether the speed camera behind a fine was approved and within validity on the ticket date. Platform-hosted, no credentials, pay per query with prepaid credit.

- 📊 **1 tool**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Consulta de Radar (PSIE/Inmetro)`, URL `https://api.mcp.ai/p_psie`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=psie&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9wc2llIn0=)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=psie&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_psie%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_psie
```

---

## 1 tool

| Tool | Description |
|---|---|
| `psie_consulta_municipio` | Lista os instrumentos do Inmetro (radares/medidores de velocidade por padrão) de um município e a situação metrológica de cada um: Nº de Série, Sentido, Vel. |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_psie` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
