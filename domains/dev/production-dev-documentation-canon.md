---
canonical: true
id: production-dev-documentation-canon
title: "Canônico de Documentação Técnica — Produção & Dev"
scope: "documentação técnica para projetos web (base template)"
priority: "high"
version: "1.0"
date: "2026-02-08"
inherits_from: global-canon
description: "Documento canônico que define quais artefatos de documentação técnica devem existir para suportar o desenvolvimento, implantação e operação de um webapp, e como organizá-los como base para outros projetos."
---

# Canônico de Documentação Técnica — Produção & Dev

## Objetivo

Fornecer um template canônico para projetos web que indica os documentos mínimos recomendados, sua finalidade, onde armazená-los no repositório e um breve esquema de conteúdo para cada um. Este repositório serve como base e referência para outros projetos.

## Requisitos

- Seguir o `Canônico Global` em caso de conflito.
- Cada documento deve ser escrito em Markdown, legível em texto puro e possuir metadata (front matter) indicando `id`, `version`, `date` e `status` (draft|stable|deprecated).
- Documentos grandes devem conter sumário (TOC) e exemplos práticos.

## Estrutura recomendada de diretórios

- `docs/architecture/` — Documentação de arquitetura
- `docs/stack/` — Stack tecnológica e infra
- `docs/db/` — Modelagem e operações de banco de dados
- `docs/api/` — APIs, contratos e exemplos
- `docs/requirements/` — Requisitos e especificações funcionais
- `docs/processes/` — Processos técnicos e runbooks
- `docs/governance/` — Padrões, políticas e governança

## Documentos recomendados (lista e breve descrição)

1. Arquitetura do Sistema (`docs/architecture/architecture-overview.md`)
   - Visão de alto nível (componentes, fluxos, responsabilidades)
   - Diagramas (componentes, sequência, deployment)
   - Requisitos não funcionais esp. (escalabilidade, disponibilidade, RTO/RPO)
   - Decisões arquiteturais (ADR links) e trade-offs

2. Visão Técnica / Stack (`docs/stack/stack-overview.md`)
   - Tecnologias principais (backend, frontend, DB, filas, cache)
   - Versões, rationale e alternativas consideradas
   - Estratégia de deploy (CI/CD), ambientes (dev/staging/prod)
   - Dependências externas e contratos (3rd-party)

3. Banco de Dados (`docs/db/db-design.md`)
   - Modelo lógico e físico (ERDs)
   - Estratégia de migrations e versionamento
   - Estratégia de backups, restauração e manutenção
   - Índices, partições, políticas de retenção e operações custosas

4. API & Contratos (`docs/api/api-reference.md`)
   - Contratos HTTP/REST ou GraphQL schema; exemplos de payload
   - Autenticação/autorização (JWT, OAuth2, scopes)
   - Exemplos de uso, mocks e collection (Postman/Insomnia)
   - SLAs e limites de taxa (rate limits)

5. Requisitos e Funcionalidades (`docs/requirements/specs.md`)
   - Lista de features com descrição, critérios de aceitação e prioridade
   - Fluxos de usuário (user journeys)
   - Regras de negócio e validações

6. Processos Técnicos e Runbooks (`docs/processes/runbooks.md`)
   - Procedimentos de deploy (step-by-step)
   - Runbooks de incidentes (detecção, triagem, mitigação, rollback)
   - Monitoramento e alertas (métricas chave, dashboards)

7. Padrões, Linters e Governança (`docs/governance/standards.md`)
   - Convenções de codificação (links para ESLint, Stylelint, PHP-CS, etc.)
   - Política de branches, PR checks, releases e versionamento
   - Regras de segurança, secrets management e políticas de acesso

8. Observabilidade e Operações (`docs/ops/observability.md`)
   - Métricas, logs, tracing (OpenTelemetry), dashboards e SLIs/SLOs
   - Estratégia de retenção de logs e custo estimado

9. Segurança e Compliance (`docs/governance/security.md`)
   - Requisitos de segurança, checklist de hardening
   - Gestão de segredos, criptografia em trânsito e repouso
   - Processo de gestão de vulnerabilidades e resposta

10. Guia de Onboarding e Developer Experience (`docs/processes/onboarding.md`)
    - Como configurar ambiente local, executar testes, workflow de PR
    - Ferramentas, atalhos e melhores práticas para novos desenvolvedores

## Metadados e controle de versão

- Cada documento deve ter front matter com pelo menos: `id`, `title`, `version`, `date`, `status`, `authors`.
- Manter um arquivo `docs/README.md` que aponte para os principais canônicos e o estado de maturidade (draft/stable).

## Modelos e templates

- Fornecer modelos simples para: ADR (Architectural Decision Record), template de runbook, template de especificação (feature), e template de contrato de API (OpenAPI).
- Recomenda-se adicionar uma pasta `docs/templates/` com arquivos `adr-template.md`, `runbook-template.md`, `spec-template.md`, `openapi-template.yaml`.

## Boas práticas

- Atualizar documentação como parte da definição de pronto (DoD) para cada mudança de feature/infra.
- Manter diagramas em formatos editáveis (ex.: draw.io / diagrams.net) junto com export PNG/SVG para renderização.
- Incentivar revisão de documentação em PRs (checks automatizados).

## Exemplo de checklist mínimo para cada PR de feature

- [ ] Atualizar `docs/requirements` se houver mudança de comportamento
- [ ] Adicionar/atualizar API contract se aplicável
- [ ] Atualizar runbook/deployment se processo impactado
- [ ] Executar linters e corrigir violações

## Conclusão

Este canônico fornece a lista mínima e estrutura para documentação de um webapp abrangente. Ele deve ser adaptado por projetos filhos conforme necessidades específicas, mantendo a hierarquia de canônicos (Global → Domínio → Formato → Projeto).
