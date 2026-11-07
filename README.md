# `.github` — repositório da organização

Este é o repositório **especial** da org (`github.com/fbso-techservice/.github`).
O GitHub usa o conteúdo daqui como **default** para todos os repositórios da
organização — mas **não** é um repositório de código.

## O que vive aqui

| Pasta/arquivo | Papel |
|---|---|
| `profile/README.md` | Página pública da organização (`github.com/fbso-techservice`) |
| `CONTRIBUTING.md` | Guia de contribuição default (linka `platform/standards`) |
| `SECURITY.md` | Política de segurança default (linka `platform/standards/security`) |
| `GOVERNANCE.md` | Governança: semver, ADR, donos, "promover genérico / manter específico" |
| `ISSUE_TEMPLATE/` | Templates de issue default (bug, feature, user story) |
| `PULL_REQUEST_TEMPLATE/` | Template de PR default |
| `workflow-templates/` | "Starter workflows" — **copiados** no bootstrap de um repo |

## O que NÃO vive aqui

- **Reusable workflows / composite actions** → ficam em [`platform/.github/`](../platform/README.md)
  e são **chamados** via `uses:`, não copiados.
- **`CODEOWNERS`** → não existe em nível de org; vai **por repositório**.

## Distinção importante

| Mecanismo | Onde | Chamado ou copiado? |
|---|---|---|
| `workflow-templates/` (aqui) | este repo | **copiado** 1× no bootstrap |
| reusable workflows (`on: workflow_call`) | `platform/.github/workflows/` | **chamado** em runtime via `uses:` |
