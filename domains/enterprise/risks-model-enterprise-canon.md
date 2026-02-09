---
title: Modelo de Gestão de Riscos - Canon
status: draft
version: 1.0.0
owner: risk@empresa
created: 2026-02-09
review_cycle: 6m
---

# Modelo de Gestão de Riscos — Regras Canônicas

Objetivo: estabelecer um padrão para identificação, avaliação, classificação e mitigação de riscos em nível enterprise.

Formato e nome de arquivo
- Formato: Markdown; anexos (planilhas, matrizes) como CSV/XLSX em `assets/`.
- Nome sugerido: `risks.modelo.<area>.md`.
- Frontmatter obrigatório: `title`, `status`, `version`, `owner`, `created`, `review_cycle`.

Conteúdo mínimo
1. Resumo executivo
2. Metodologia de identificação e avaliação (escala de probabilidade e impacto)
3. Matriz de riscos atual (tabela com id, descrição, categoria, probabilidade, impacto, score)
4. Controles existentes e gaps
5. Plano de mitigação (ações, responsáveis, prazos)
6. Indicadores de risco (KRIs) e triggers
7. Processo de monitoramento e reporte

Classificação e critérios
- Utilizar classificação padrão: Baixo / Médio / Alto / Crítico.
- Definir thresholds numéricos para score (ex.: probabilidade * impacto).

Responsabilidades
- Owner: Segurança da Informação / Gestão de Riscos.
- Revisores: Operações, Finanças, Jurídico quando aplicável.

Critérios de aceitação
- Matriz de riscos preenchida com pelo menos os principais 10 riscos por área.
- Planos de mitigação atribuídos com responsáveis e prazos.
- Frequência de reporte definida.

Histórico
- 2026-02-09 — v1.0.0 — Regras canônicas criadas.
