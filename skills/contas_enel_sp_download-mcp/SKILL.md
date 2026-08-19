---
name: contas_enel_sp_download-mcp
description: Skill da REST API do Enel SP: Download na MCP.AI: 1 endpoint em /api/contas_enel_sp_download. Enel SP: Download, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Enel SP: Download — REST API skill

Você tem acesso à **Enel SP: Download** REST API na MCP.AI.

> Enel SP: Download, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/contas_enel_sp_download
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
curl -X POST https://api.mcp.ai/api/contas_enel_sp_download/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"login_email":"...","login_senha":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/contas_enel_sp_download/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `contas_enel_sp_download_consultar`

Enel SP: Download, consulta em fonte oficial. _(POST /api/contas_enel_sp_download/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `login_email` | string | Sim | Parâmetro de consulta "login_email". |
| `login_senha` | string | Sim | Parâmetro de consulta "login_senha". |
| `instalacao` | string | Não | Parâmetro de consulta "instalacao". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_contas_enel_sp_download` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
