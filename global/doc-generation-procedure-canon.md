---
title: Procedimento Canônico de Geração Interativa de Documentos e Código
status: draft
version: 1.0.0
owner: governance@empresa
created: 2026-02-09
review_cycle: 12m
---

# Procedimento Canônico de Geração Interativa de Documentos e Código

Objetivo

Definir um procedimento padrão e interativo que o assistente (chat) deve seguir sempre que auxiliar na criação de documentos textuais baseados em templates canônicos Markdown ou na geração de código. O fluxo garante maior alinhamento com o objetivo do autor, reduz retrabalho e registra decisões importantes.

Escopo

Aplica-se a: todos os fluxos de criação de documentos Markdown canônicos e geração de código gerados por assistentes automatizados dentro desta organização.

Princípios gerais

- Interatividade controlada: o assistente pergunta UMA questão por vez e espera a resposta do usuário antes de prosseguir.
- Sugestões didáticas: para cada pergunta o assistente apresenta pelo menos 3 sugestões de resposta (cada uma com explicação curta e, quando aplicável, um exemplo concreto).
- Aceitação de resposta livre: o usuário pode responder livremente (texto aberto) em vez de escolher uma sugestão.
- Confirmação periódica: ao final de cada bloco lógico (ex.: seções principais do documento; ou uma parte do código) o assistente apresenta um resumo e pede confirmação antes de gerar o próximo bloco.
- Registro de decisões: todas as escolhas críticas (ex.: formato, público, restrições técnicas) devem ser gravadas no frontmatter YAML ou em uma seção `Decisions` do documento.

Fluxo recomendado — Documentos (Markdown)

1) Início: o assistente inicia com a pergunta fundamental:
   "Qual o objetivo principal deste documento?"
   - Fornecer ≥3 sugestões de resposta, com explicação e exemplo, por exemplo:
     a) Resumo executivo para diretoria — Explicação: 1 página, linguagem de alto nível; Ex.: "Resumo para CEO".
     b) Procedimento operacional (SOP) — Explicação: passo-a-passo, checklists; Ex.: "Checklist de deploy".
     c) Material de treinamento — Explicação: linguagem didática, exemplos e exercícios; Ex.: "Manual do colaborador".

2) Perguntas subsequentes (cada uma feita uma a uma, com ≥3 sugestões):
   - Público-alvo (quem lerá e tom da linguagem).
   - Extensão desejada (curto 1-2p / médio 3-10p / longo >10p).
   - Nível de detalhe técnico (alto / médio / baixo) e anexos esperados.
   - Formato e template preferido (usar `docs/templates/` ou custom).
   - Restrições (informações sensíveis, linguagem, conformidade).

3) Geração incremental:
   - Depois de coletar respostas para as perguntas principais, o assistente gera o rascunho da primeira seção (Resumo Executivo ou Introdução) e pede revisão.
   - Após aprovação da seção, pergunta se deve continuar com a próxima seção (ex.: Propósito, Escopo, Responsabilidades).
   - Repetir até completar todas as seções mínimas do template.

4) Finalização:
   - Gerar frontmatter final (preenchendo `title`, `owner`, `status`, `version`, `created`, `review_cycle` e `decisions` onde pertinente).
   - Inserir seção `Histórico de versões` e `Decisions` com data, autor e resumo das escolhas.
   - Perguntar se deseja gerar variantes (resumo curto, versão para treinamento, versão para auditoria).

Fluxo recomendado — Geração de Código

Objetivo: reduzir retrabalho dividindo a entrega em partes e validando arquitetura e decisões antes de implementar.

1) Fase 1 — Design/Especificação (pergunta inicial):
   - "Qual o objetivo do componente/sistema que deseja gerar?"
   - Sugestões (com exemplos):
     a) Biblioteca reutilizável (explicação: API pública, testes, documentação) — Ex.: utilitários de data.
     b) Serviço web (explicação: endpoints, autenticação, persistência) — Ex.: API REST para usuários.
     c) Script pontual (explicação: execução única ou agendada) — Ex.: migração de dados.

   - Perguntas seguintes (uma a uma): linguagem/stack, requisitos não-funcionais (performance, segurança), dependências, restrições de licença.

   - Entregar: arquivo de especificação/README com endpoints, modelos de dados e contratos de interface. Pedir confirmação.

2) Fase 2 — Esqueleto/Scaffolding
   - Gerar estrutura de pastas, arquivos principais, CI básico e placeholders.
   - Apresentar a lista de arquivos que serão criados e perguntar aprovação antes de escrever o código.

3) Fase 3 — Implementação por partes
   - Implementar uma unidade funcional por vez (ex.: endpoint A, depois endpoint B) — antes de cada unidade: perguntar se deve implementar e oferecer opções de implementação (3 abordagens com trade-offs).

4) Fase 4 — Testes
   - Gerar testes unitários e de integração; pedir ao usuário priorizar cobertura/áreas críticas.

5) Fase 5 — Documentação e Deployment
   - Gerar README final, instruções de deploy e comandos.

Templates de perguntas padrão (exemplos)

- Objetivo principal: (3 sugestões + explicação)
- Público-alvo: (interno / executivo / cliente final)
- Escopo: (o que incluir/excluir)
- Formato/estilo: (template de docs, tamanho, anexos)
- Restrições técnicas/regulatórias
- Critério de aceitação: (o que significa "pronto")

Exemplo de diálogo (documento)

Assistente: "Qual o objetivo principal deste documento?" — Sugestões: a) Resumo executivo..., b) SOP..., c) Material de treinamento... (cada com explicação e exemplo).
Usuário: "b) SOP"
Assistente: "Quem é o público-alvo?" — Sugestões: a) operador de campo..., b) gestor de turno..., c) auditor interno....
Usuário responde. Assistente gera seção `Resumo` e pergunta: "Deseja revisar/editar o resumo antes de continuar?"

Exemplo de diálogo (código)

Assistente: "Qual é o objetivo do componente?" — Sugestões: a) Biblioteca reutilizável..., b) Serviço web..., c) Script pontual...
Usuário: escolhe.
Assistente: "Qual linguagem/stack prefere?" — Sugestões com trade-offs.
Usuário: responde.
Assistente: gera SPEC/README e pergunta "Confirmar arquitetura e prosseguir para scaffolding?".

Frontmatter e registro de decisões

- Recomenda-se adicionar no frontmatter um campo `decisions` com pares chave/valor resumindo escolhas críticas (ex.: `target_audience: operadores`, `document_type: SOP`, `tech_stack: python/fastapi`).

Critérios de aceitação do procedimento

- Assistente sempre pergunta 1 questão por vez.
- Cada pergunta apresenta ≥3 sugestões com explicações.
- Respostas do usuário podem ser livres.
- Decisões críticas são registradas no documento.
- Geração de código segue as fases design→scaffold→implementação→testes.

Como utilizar e onde referenciar

- Este arquivo deve ficar em `global/doc-generation-procedure-canon.md`.
- Documentos canônicos e templates (em `docs/templates/` e `domains/*`) devem referenciar este procedimento quando exigirem interação com o assistente.
- Recomenda-se adicionar link para este procedimento nos README das subpastas de domínio.

Anexos — Modelos prontos (exemplos)

- Exemplo de frontmatter mínimo gerado automaticamente:

  ---
  title: "Título do documento"
  owner: "time@empresa"
  status: draft
  version: 0.1.0
  created: 2026-02-09
  review_cycle: 12m
  decisions:
    document_type: "SOP"
    target_audience: "operadores"
  ---

- Exemplo de checklist de perguntas para documentos:
  1. Objetivo principal
  2. Público-alvo
  3. Escopo (incluir/excluir)
  4. Formato e templates
  5. Nível de detalhe
  6. Riscos/controles

Histórico
- 2026-02-09 — v1.0.0 — Procedimento canônico criado.
