# Política de Segurança

Política default da FBSO TechServices.

## Baseline

A linha de base de segurança (LGPD, RBAC/SSO, multi-tenancy, auditoria) vive na
plataforma — **fonte única, não duplicar**:

- `platform/standards/security/SECURITY.md` — baseline
- `platform/standards/security/lgpd-checklist.md`
- `platform/standards/security/threat-model-template.md`

## Reportando vulnerabilidades

Reporte vulnerabilidades de forma privada via GitHub Security Advisory do repositório
afetado (aba **Security → Report a vulnerability**). Não abra issue pública.

## Gates no pipeline

SAST, secret scan e ZAP rodam como reusable workflows da `platform` (ver
`platform/.github/workflows/`). Os repositórios de produto os invocam via `uses:`.
