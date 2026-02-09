title: "Modelo Canon — Documento Profissional Empresarial"
status: draft
version: 1.0.0
owner: docs@empresa
created: 2026-02-09
review_cycle: 12m

# Modelo Canon — Documento Profissional Empresarial

Este modelo descreve a estrutura, regras de redação e formatação para documentos profissionais corporativos destinados a produção em Word (.docx) e exportação para PDF. O conteúdo segue orientações ABNT relevantes e prioriza linguagem narrativa, detalhista e lógica, com parágrafos concisos e interligados.

## Capa

---
title: Procedimento Canônico de Geração Interativa de Documentos e Código
status: draft
version: 1.1.0
owner: governance@empresa
created: 2026-02-09
review_cycle: 12m
---

# Procedimento Canônico de Geração Interativa de Documentos e Código

## 1. Objetivo

Definir um fluxo interativo e padronizado que o assistente automatizado deve seguir ao gerar documentos canônicos e artefatos de código. O procedimento tem como objetivo reduzir retrabalho, garantir consistência editorial e técnica, e registrar decisões críticas para auditoria e rastreabilidade. Aplicam-se validações incrementais que exigem confirmação explícita do autor antes de cada entrega parcial.

## 2. Escopo

Este procedimento aplica-se a todos os fluxos de criação de documentos Markdown canônicos e à geração de código quando realizados por assistentes automatizados integrados às práticas da organização. Não cobre conteúdo produzido manualmente sem uso do assistente, exceto quando for necessário integrar esses artefatos a templates canônicos ou quando houver automação declarada.

## 3. Princípios

Interatividade controlada: o assistente deve formular UMA pergunta por vez e aguardar a resposta do usuário antes de prosseguir. Isso evita ambiguidades, permite decisões informadas e reduz retrabalho causado por múltiplas escolhas feitas sem confirmação.

Sugestões didáticas: para cada pergunta o assistente apresenta pelo menos três opções com explicação e exemplo prático. A prática facilita a tomada de decisão pelo autor e torna explícitos trade-offs entre alternativas.

Aceitação de resposta livre: o usuário pode fornecer respostas em texto livre, que devem ser aceitas e registradas. O assistente deve validar respostas quando relevante (ex.: formatos, valores permitidos) e oferecer correções sugeridas.

Confirmação periódica: ao final de cada bloco lógico (por exemplo, uma seção principal do documento ou um conjunto de endpoints) o assistente apresenta um resumo das decisões tomadas e solicita confirmação escrita antes de gerar o próximo bloco. A confirmação é obrigatória para avanços que alterem arquitetura ou escopo.

Registro de decisões: todas as escolhas críticas (formato, público, restrições técnicas, stack) devem ser registradas no frontmatter YAML ou em uma seção `Decisions` do documento, com data e autor. Esse registro é requisito para versões oficiais e para rastreabilidade de auditoria.


## 4. Fluxos

### 4.1 Documentos (Markdown)

1) Início: o assistente inicia com a pergunta fundamental: "Qual o objetivo principal deste documento?". Para cada pergunta, o assistente apresenta ao menos três sugestões com explicação e exemplo prático, e aceita respostas em texto livre quando necessário.

2) Perguntas subsequentes: o assistente coleta, uma a uma, informações como público-alvo, extensão desejada, nível de detalhe técnico, template preferido e restrições (informações sensíveis e conformidade). Cada pergunta deve incluir opções explicadas e implicações para o conteúdo gerado.

3) Geração incremental: após coletar as entradas principais, o assistente gera o rascunho da primeira seção (por exemplo, Resumo Executivo ou Introdução) e solicita revisão. Somente após aprovação explícita do autor, o assistente avança para a próxima seção.

4) Finalização: o assistente gera o frontmatter final (preenchendo `title`, `owner`, `status`, `version`, `created`, `review_cycle` e `decisions` quando aplicável), adiciona `Histórico de versões` e `Decisions` com data/autor e pergunta se o usuário deseja variantes do documento (resumo curto, versão para treinamento, versão para auditoria).

### 4.2 Geração de Código

Objetivo: reduzir retrabalho dividindo a entrega em fases e validando arquitetura e decisões antes da implementação.

1) Fase 1 — Design/Especificação: o assistente pergunta o objetivo do componente/sistema e apresenta abordagens (por exemplo: biblioteca reutilizável, serviço web, script pontual), com exemplos e trade-offs. Em seguida coleta linguagem/stack, requisitos não-funcionais, dependências e restrições de licença e gera um SPEC/README para confirmação.

2) Fase 2 — Esqueleto/Scaffolding: o assistente propõe a estrutura de pastas, arquivos principais, CI básico e placeholders; apresenta a lista de arquivos que serão criados e solicita aprovação antes de escrever código.

3) Fase 3 — Implementação por partes: implementar unidades funcionais isoladas (por ex., endpoint A), sempre solicitando confirmação e oferecendo 3 abordagens com trade-offs quando relevante.

4) Fase 4 — Testes: gerar testes unitários e de integração e priorizar áreas de cobertura conforme orientação do usuário.

5) Fase 5 — Documentação e Deployment: gerar README final, instruções de deploy e comandos de execução.

Templates de perguntas padrão (exemplos)

- Objetivo principal: (3 sugestões + explicação)
- Público-alvo: (interno / executivo / cliente final)
- Escopo: (o que incluir/excluir)
- Formato/estilo: (template de docs, tamanho, anexos)
- Restrições técnicas/regulatórias
- Critério de aceitação: (o que significa "pronto")

Exemplos de diálogo (documento)

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

### Considerações Finais ou Observações Técnicas

Limitações, premissas, decisões relevantes ou pontos de atenção.

Se o documento for extenso, a estrutura pode ser expandida, mas nunca reduzida.


## 5. Regras de Profundidade e Escrita

### 5.1 Parágrafos

Cada seção principal deve conter no mínimo três parágrafos completos.

Cada subseção deve conter no mínimo dois parágrafos completos.

Parágrafos devem ser explicativos e narrativos, não meramente introdutórios.

Não é permitido substituir parágrafos por listas extensas.

### 5.2 Tópicos e Listas

Listas devem ser usadas somente para:

- exemplos
- checklists
- enumeração objetiva de itens

Listas nunca devem ser o conteúdo principal da seção.

Sempre que houver lista, deve haver texto explicativo antes e depois.

## 6. Linguagem e Tom Técnico

A linguagem deve ser técnico-descritiva, clara e precisa. Use voz ativa e instruções objetivas.

Evitar termos genéricos sem explicação (por exemplo: “eficiente”, “moderno”, “robusto”). Quando usados, acompanhe justificativa técnica.

Não utilizar linguagem promocional ou de marketing, emojis, humor ou informalidades.

O texto deve ser compreensível por um profissional técnico que não participou do projeto, fornecendo contexto suficiente para entendimento e ação.

## 7. Layout e Organização Visual

Títulos e subtítulos devem seguir hierarquia lógica e facilitar navegação (por exemplo, H2 para seções principais, H3 para subseções).

Evitar seções excessivamente longas sem subdivisão; prefira fragmentação em subseções claras quando necessário.

Manter espaçamento visual consistente entre blocos conceituais para leitura rápida.

Código, quando necessário, deve ser claramente delimitado e sempre acompanhado de explicação textual que descreva propósito e parâmetros.

## 8. Regras de Conteúdo Técnico

Ao documentar qualquer componente técnico, sempre que aplicável, deve-se abordar as seguintes dimensões:

- Finalidade: por que isso existe.
- Contexto: onde se encaixa no sistema.
- Decisões técnicas: por que foi escolhido.
- Impactos: vantagens, limitações e riscos.
- Dependências: integrações ou pré-requisitos.

Se alguma dessas dimensões não puder ser descrita, isso deve ser explicitado e justificado.

## 9. Validação Obrigatória Antes da Entrega

Antes de finalizar um documento técnico, verificar:

- A estrutura mínima foi respeitada?
- Cada seção principal tem ao menos três parágrafos?
- As listas são complementares, não dominantes?
- As decisões técnicas estão explicadas?
- Não há suposições implícitas sem justificativa?

Histórico
- 2026-02-09 — v1.1.0 — Reescrita de Objetivo/Escopo/Princípios; renumeração e inclusão de regras de escrita e validação.
- 2026-02-09 — v1.0.0 — Procedimento canônico criado.

