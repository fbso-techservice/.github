# Governança de repositórios — FBSO TechServices

## Topologia

```
github.com/fbso-techsolutions/
├── .github/              metadados da org (templates, health)
├── platform-standards/   constituição corporativa (padrões, regras, blueprints)
├── saas-<produto>/       produtos (monorepo de produto)
├── svc-<domínio>/        soluções cross deployáveis (serviços)
└── lib-<nome>/           soluções cross importáveis (SDKs/parsers)
```

## Taxonomia de repositórios

| Prefixo | Categoria | Critério |
|---|---|---|
| `.github` | metadados da org | templates, health files |
| `platform-standards` | **constituição** | docs + blueprints, **não** roda código de negócio |
| `saas-` | produto | vendável |
| `svc-` | solução cross **deployável** | tem runtime/compliance |
| `lib-` | solução cross **importável** | SDK/parser, sem runtime |
| `client-` | projeto de consultoria | (futuro) |

## Regras

1. **"Promover o genérico, manter o específico."** O que é igual entre ≥2 SaaS sobe para
   `platform-standards/`; cada produto guarda só o delta e **linka** (nunca copia).
2. **Constituição é `platform-standards`.** Nenhum código de negócio cross entra nele —
   deployável vai para `svc-*`, importável para `lib-*`.
3. **Repo = fronteira de deploy + compliance + homologação.** Compliance isolável
   (PCI-DSS, BCB, SEFAZ) ⇒ repo individual; mesmos protocolos/adapters ⇒ repo por família.
4. **Um documento vive em um só lugar** ("ponteiros, não volume"). Links cross-repo usam
   URL absoluta do GitHub.
5. **Trunk-based + PR review obrigatório.** Convenções em
   `platform-standards/standards/engineering/`.

## Contrato de solução

Toda solução `svc-*` publica: **contrato OpenAPI + client SDK + eventos/webhooks**.
Consumidores usam o SDK, nunca chamam o fornecedor direto.

## Donos

| Repo | Dono |
|---|---|
| `platform-standards` | Tech lead + Arquitetura + Cloud & DevOps |
| `saas-<produto>` | Squad do produto |
| `svc-<domínio>` | Engenharia/Arquitetura (transversal) |
