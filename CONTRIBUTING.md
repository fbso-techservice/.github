# Contribuindo

Guia de contribuição default da FBSO TechServices.

## Onde estão as regras

As regras completas vivem na **plataforma** (fonte única — não duplicar aqui):

- **Processo (agile/waterfall):** `platform-standards/standards/agile/`
- **Engenharia (coding standards, commits, branches):** `platform-standards/standards/engineering/`
- **Arquitetura (guardrails: tenant_id, RLS, API-First):** `platform-standards/standards/architecture/`

> Regra: **"promover o genérico, manter o específico."** O que for transversal a mais
> de um SaaS sobe para `platform-standards/`; cada produto guarda só o delta e linka a plataforma.

## Fluxo mínimo

1. Abra uma issue (use os templates da org).
2. Crie uma branch a partir de `main` (trunk-based).
3. Abra um PR com descrição no template da org.
4. PR review obrigatório antes do merge.

Detalhes de convenção de commits/branches: `platform-standards/standards/engineering/`.
