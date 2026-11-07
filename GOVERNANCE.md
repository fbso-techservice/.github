# Governança de repositórios — FBSO TechServices

## Topologia

```
github.com/fbso-techservice/
├── .github/          metadados/templates da org (este repo)
├── platform/         fundação de engenharia (transversal)
└── saas-<produto>/   1 repo por produto (monorepo de produto)
```

## Regras

1. **"Promover o genérico, manter o específico."** O que é igual entre ≥2 SaaS sobe
   para `platform/`; cada produto guarda só o delta e **linka** (nunca copia).
2. **Plataforma é produto.** `platform/` segue semver + changelog + ADRs; mudanças
   são versionadas e os produtos fazem upgrade deliberado.
3. **Um documento vive em um só lugar** ("ponteiros, não volume"). Links cross-repo
   usam URL absoluta do GitHub.
4. **Trunk-based + PR review obrigatório.** Convenções em `platform/standards/engineering/`.

## Nomenclatura de repositórios

| Prefixo | Categoria |
|---|---|
| `saas-` | Produtos SaaS próprios |
| `platform` | Fundação interna (único) |
| `.github` | Metadados da org (único) |
| `client-` | Projetos de consultoria por cliente (futuro) |

## Donos

| Repo | Dono |
|---|---|
| `platform` | Tech lead + Arquitetura + Cloud & DevOps |
| `saas-<produto>` | Squad do produto |
