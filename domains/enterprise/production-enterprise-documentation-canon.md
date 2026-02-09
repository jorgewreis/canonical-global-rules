# Documentação base para empresas

Objetivo: definir a estrutura mínima, os artefatos e os padrões que devem ser criados para a documentação de produção em nível enterprise.

## Visão geral

Este documento descreve os documentos essenciais (artefatos), a responsabilidade, o formato e as regras de governança para a documentação de produção da organização. A partir de agora todos os documentos devem seguir as regras gerais definidas em `global/00-global-canon.md` e os padrões de arquivo e estilo descritos em `formats/` (ex.: `markdown-format-canon.md`, `html-format-canon.md`).

## Escopo

- Abrange documentação estratégica e operacional aplicada à produção enterprise.
- Não substitui políticas legais formais; referencia-as quando aplicável.

## Público-alvo

- Líderes de domínio, gestores de produto, equipes de operações, segurança, finanças e conformidade.

## Convenções e formatos obrigatórios

- Formato de arquivo: Markdown para documentos textuais (seguir `formats/markdown-format-canon.md`).
- Nomes de arquivo: <entidade>.<artefato>.md (ex.: `financeiro.plano-financeiro.md`).
- Frontmatter: todo documento deve iniciar com metadados YAML contendo pelo menos: `title`, `status`, `version`, `owner`, `created`, `review_cycle`.
- Estrutura de tópicos: comece com um resumo executivo, depois propósito, escopo, responsabilidades, conteúdo principal (seções específicas por artefato), observações de governança e histórico de versões.

> Note: Utilize os templates em `docs/templates/` quando houver correspondência (ex.: `api-template.md`, `architecture-template.md`).

## Artefatos essenciais (o que deve ser criado)

Cada artefato listado abaixo deve ser produzido como um documento separado, com seu próprio frontmatter e responsável claro.

1) Documento de Visão e Missão
	- Propósito: registrar objetivos estratégicos, valores e propósito do produto/área.
	- Conteúdo mínimo: visão, missão, objetivos estratégicos (OKRs / metas), alinhamento com roadmap empresarial.
	- Owner: executivo de área / PO.
	- Formato: `vision-mission.<area>.md`.
	- Frequência de revisão: anual ou quando houver mudança estratégica.

2) Organograma e RACI (Organograma Funcional)
	- Propósito: descrever estrutura organizacional, papéis, responsabilidades e linhas de reporte.
	- Conteúdo mínimo: diagrama (link ou imagem), tabela de papéis com responsabilidades, RACI por processos críticos.
	- Owner: RH / gestão de operações.
	- Formato: `orgchart.<area>.md` (incluir imagem em `assets/` quando aplicável).

3) Políticas de Governança
	- Propósito: definir diretrizes de tomada de decisão, compliance, ética e aprovação de mudanças.
	- Conteúdo mínimo: princípios, autoridade de aprovação, processos de exceção, requisitos de conformidade.
	- Owner: Comitê de Governança / Jurídico.
	- Formato: `governance.politicas.<area>.md`.

4) Modelo de Gestão de Riscos
	- Propósito: identificar, classificar e mitigar riscos operacionais, financeiros e legais.
	- Conteúdo mínimo: matriz de riscos, critérios de impacto e probabilidade, controles existentes, plano de mitigação.
	- Owner: Segurança da Informação / Gestão de Riscos.
	- Formato: `risks.modelo.<area>.md`.

5) Plano Financeiro Base
	- Propósito: apresentar estrutura de custos, fontes de receita, projeções e indicadores financeiros básicos (run-rate, burn, margem).
	- Conteúdo mínimo: resumo executivo financeiro, premissas, projeções trimestrais/anuais, KPIs, fontes de financiamento.
	- Owner: Finanças / Contabilidade.
	- Formato: `financeiro.plano-financeiro.<area>.md`.

## Metadados e controle de versão

- Exemplo mínimo de frontmatter YAML:

  ---
  title: "Título do documento"
  owner: "time@empresa"
  status: draft | review | approved
  version: 0.1.0
  created: 2026-02-09
  review_cycle: 12m
  ---

- Histórico: inclua uma seção `Histórico de versões` com data, autor e resumo das mudanças.

## Critérios de aceitação dos documentos

- Documento possui frontmatter completo.
- Owner claramente indicado e disponível para revisão.
- Objetivos e escopo descritos.
- Conteúdo mínimo (conforme artefato) preenchido.
- Revisão e publicação conforme processo de governança (link para `governance.politicas` quando aplicável).

## Como criar e publicar

1. Escolher template apropriado em `docs/templates/` ou usar a estrutura mínima deste arquivo.
2. Preencher frontmatter e conteúdo seguindo `formats/markdown-format-canon.md`.
3. Salvar com o padrão de nome definido e colocar em pasta correspondente ao domínio (`domains/<dominio>/`).
4. Abrir PR com etiqueta `docs` e atribuir o owner para revisão.
5. Após aprovação, marcar `status: approved` e atualizar `version`.

## Governança e revisão

- Cada documento deve ter um ciclo de revisão (`review_cycle`) e um owner responsável por convocar revisões.
- Alterações significativas exigem aprovação pelo comitê de governança (ver `Políticas de Governança`).

## Itens a serem produzidos imediatamente

- Criar os cinco artefatos essenciais listados nesta seção para cada domínio crítico (ex.: produção, segurança, financeiro).
- Fornecer owner, artefato inicial (mesmo que rascunho) e data de primeira revisão.

## Referências

- `global/00-global-canon.md` — regras globais de documentação.
- `formats/` — padrões de formato e estilo (Markdown, HTML, CSS, etc.).
- `docs/templates/` — modelos recomendados para documentos específicos.
 - `global/doc-generation-procedure-canon.md` — procedimento canônico de geração interativa de documentos e código (Q&A uma-pergunta-por-vez, sugestões didáticas e etapas de geração).

## Artefatos canônicos relacionados (pasta `domains/enterprise`)

- `vision-mission-enterprise-canon.md` — regras canônicas para Documento de Visão e Missão.
- `orgchart-enterprise-canon.md` — regras canônicas para Organograma e RACI.
- `governance-policies-enterprise-canon.md` — regras canônicas para Políticas de Governança.
- `risks-model-enterprise-canon.md` — regras canônicas para Modelo de Gestão de Riscos.
- `finance-plan-enterprise-canon.md` — regras canônicas para Plano Financeiro Base.

## Documentação específica por empresa (subpastas em `domains/enterprise/`)

Cada empresa possui uma subpasta com templates canônicos específicos que complementam os artefatos globais acima. Referencie e use esses templates ao criar documentação específica da empresa.

- `domains/enterprise/florattai/`
	- `catalogo-produtos-florattai-canon.md` — linhas de produto, descrição técnica, público-alvo e USP.
	- `registro-composicoes-florattai-canon.md` — fórmulas, proporções, segurança química e fornecedores.
	- `estrategia-expansao-florattai-canon.md` — avaliação de novos produtos e requisitos regulatórios (ex.: ANVISA).
	- `manual-branding-florattai-canon.md` — identidade visual e posicionamento.

- `domains/enterprise/jorge-reis-drones/`
	- `manual-operacoes-jorge-reis-canon.md` — protocolos de voo, checklists e manutenção.
	- `documentacao-legal-jorge-reis-canon.md` — licenças (ANAC/DECEA), contratos e termos.
	- `processos-comerciais-jorge-reis-canon.md` — orçamentos, precificação e relatórios pós-evento.
	- `gestao-riscos-jorge-reis-canon.md` — planos para clima, falhas técnicas e privacidade.

- `domains/enterprise/reis-artistics/`
	- `guia-criacao-reis-artistics-canon.md` — regras de composição, métrica e uso de IA.
	- `processo-publicacao-reis-artistics-canon.md` — fluxo de publicação, distribuição e registro (ABRAMUS/ECAD).
	- `manual-direitos-reis-artistics-canon.md` — contratos de cessão, patentes e gestão de royalties.
	- `estrategia-divulgacao-reis-artistics-canon.md` — métricas, canais e cronograma de divulgação.

Observação: ao criar documentos em subpastas específicas, mantenha o frontmatter obrigatório e siga os padrões de `formats/` para garantir consistência.

## Histórico

- 2026-02-09 — v1.0.0 — Reestruturação inicial para alinhamento com `global` e `formats`.
