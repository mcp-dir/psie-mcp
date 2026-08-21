---
name: psie-mcp
description: Skill da REST API do Consulta de Radar (PSIE/Inmetro) na MCP.AI: 1 endpoint em /api/psie. Consulta a situação metrológica dos radares e etilômetros de um município nas bases oficiais do Inmetro (PSIE), a mesma que o cidadão acessa: número de série, sentido, velocidade nominal, responsável, local, data de validade e resultado da verificação (aprovado, reprovado ou reparado). Útil pra checar se o radar que aplicou uma multa estava aprovado e dentro da validade na data da autuação. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Consulta de Radar (PSIE/Inmetro) — REST API skill

Você tem acesso à **Consulta de Radar (PSIE/Inmetro)** REST API na MCP.AI.

> Consulta a situação metrológica dos radares e etilômetros de um município nas bases oficiais do Inmetro (PSIE), a mesma que o cidadão acessa: número de série, sentido, velocidade nominal, responsável, local, data de validade e resultado da verificação (aprovado, reprovado ou reparado). Útil pra checar se o radar que aplicou uma multa estava aprovado e dentro da validade na data da autuação. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/psie
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/psie/consulta/municipio \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"uf":"...","municipio":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/psie/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `psie_consulta_municipio`

Lista os instrumentos do Inmetro (radares/medidores de velocidade por padrão) de um município e a situação metrológica de cada um: Nº de Série, Sentido, Vel. _(POST /api/psie/consulta/municipio)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `uf` | string | Sim | UF da infração, sigla de 2 letras (ex.: PR). |
| `municipio` | string | Sim | Nome do município da infração (ex.: TIBAGI). |
| `tipo` | integer | Não | Código do tipo de instrumento no PSIE. Default 322 = Medidor de Velocidade (radar). |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_psie` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
