---
canonical: true
id: markdown-format-canon
title: "Canônico de Formatação Markdown"
scope: "geração de arquivos em formato Markdown"
priority: "high"
version: "1.0"
date: "2026-02-08"
inherits_from: global-canon
description: "Regras canônicas para formatação Markdown; deve seguir o Canônico Global em caso de conflito."
---

# Canônico de Formatação Markdown

## 1. Finalidade do Documento

Este documento define as regras canônicas obrigatórias de formatação Markdown para qualquer artefato produzido neste formato, incluindo documentação técnica, documentação de projeto, notas de versão, READMEs, especificações e demais conteúdos estruturados em Markdown.
---
canonical: true
id: markdown-format-canon
title: "Canônico de Formatação Markdown"
scope: "geração de arquivos em formato Markdown"
priority: "high"
version: "1.0"
date: "2026-02-08"
inherits_from: global-canon
description: "Regras canônicas para formatação Markdown; deve seguir o Canônico Global em caso de conflito."
---

# Canônico de Formatação Markdown

## 1. Finalidade do Documento

Este documento define as regras canônicas obrigatórias de formatação Markdown para qualquer artefato produzido neste formato, incluindo documentação técnica, documentação de projeto, notas de versão, READMEs, especificações e demais conteúdos estruturados em Markdown.

Este canônico trata exclusivamente da forma, da sintaxe e da padronização estrutural do Markdown. Ele não define conteúdo, profundidade textual ou estilo narrativo, que são responsabilidade dos canônicos de domínio.

## 2. Referências Normativas Oficiais

A formatação Markdown deve obedecer prioritariamente às normas e boas práticas descritas nas seguintes referências:

- [Markdown Guide](https://www.markdownguide.org/)
- [Markdown Guide – Repositório GitHub](https://github.com/mattcone/markdown-guide)

Em caso de divergência entre estilos possíveis, deve-se priorizar:

- Compatibilidade com renderização no GitHub
- Clareza semântica
- Simplicidade estrutural

## 3. Princípios Gerais de Formatação

- O Markdown deve ser legível em texto puro, mesmo sem renderização.
- A estrutura deve refletir a hierarquia lógica do conteúdo.
- A sintaxe deve ser usada de forma consistente em todo o documento.
- Evitar variações estilísticas desnecessárias quando houver padrão consolidado.

## 4. Títulos e Hierarquia

### 4.1 Sintaxe Obrigatória

Títulos devem utilizar exclusivamente o símbolo `#`.

Não é permitido misturar estilos alternativos (ex.: `===`, `---`).

Exemplo:

```markdown
# Título Nível 1
## Título Nível 2
### Título Nível 3
```

### 4.2 Regras de Hierarquia

- Não pular níveis hierárquicos (ex.: `#` → `###`).
- Cada documento deve conter apenas um título de nível 1 (`#`).
- Subtítulos devem representar subdivisões conceituais reais.

## 5. Parágrafos e Quebras de Linha

- Parágrafos devem ser separados por uma linha em branco.
- Não usar múltiplas linhas em branco consecutivas.
- Quebras de linha manuais dentro de um parágrafo devem ser evitadas.

## 6. Ênfase e Destaque

### 6.1 Itálico e Negrito

- Itálico: usar `*texto*`.
- Negrito: usar `**texto**`.
- Evitar uso excessivo de ênfase.

### 6.2 Combinação

Combinação de negrito e itálico (por exemplo: `***texto***`) deve ser evitada, salvo necessidade clara.

## 7. Listas

### 7.1 Listas Não Ordenadas

- Usar exclusivamente `-` como marcador.
- Não misturar `*` ou `+`.

Exemplo:

- Item 1
- Item 2

### 7.2 Listas Ordenadas

- Usar números sequenciais.
- Evitar listas longas sem contexto textual.

Exemplo:

1. Primeiro item
2. Segundo item

### 7.3 Regras Gerais

- Listas devem ser precedidas por texto explicativo quando fizer sentido.
- Evitar listas aninhadas excessivamente profundas.

## 8. Blocos de Código

### 8.1 Blocos Multilinha

- Usar três crases (```) ao abrir e fechar blocos de código.
- Sempre que possível, especificar a linguagem.

Exemplo:

```javascript
const example = true;
```

### 8.2 Código Inline

- Usar crase simples: `` `codigo` ``.
- Evitar trechos longos como código inline.

## 9. Links

### 9.1 Sintaxe

Usar links no formato:

[Texto do link](https://exemplo.com)

### 9.2 Regras

- URLs devem ser completas (com protocolo).
- Evitar URLs soltas no corpo do texto, salvo em seções de referência.

## 10. Imagens

Usar a sintaxe padrão:

![Texto alternativo](caminho-ou-url)

O texto alternativo deve ser descritivo.
Evitar imagens sem contexto explicativo.

## 11. Tabelas

- Utilizar tabelas apenas quando agregarem clareza.
- Manter alinhamento simples e legível.

Exemplo:

| Coluna A | Coluna B |
|----------|----------|
| Valor 1  | Valor 2  |

Evitar tabelas muito largas ou complexas.

## 12. Citações (Blockquotes)

- Utilizar `>` para citações ou observações relevantes.

Exemplo:

> Esta é uma observação importante.

Não usar blockquotes para texto comum.

## 13. Comentários e Conteúdo Oculto

- Markdown não possui comentários nativos.
- Quando necessário, utilizar comentários HTML, por exemplo: `<!-- Comentário interno -->`.
- Comentários não devem interferir na leitura.

## 14. Espaçamento e Legibilidade

- Evitar linhas excessivamente longas.
- Manter espaçamento consistente entre seções.
- Evitar símbolos decorativos desnecessários.

## 15. Compatibilidade e Portabilidade

- O Markdown produzido deve renderizar corretamente no GitHub.
- Evitar extensões não suportadas amplamente, salvo exigência explícita.
- Priorizar CommonMark e GitHub Flavored Markdown (GFM).

## 16. Validação Antes da Entrega

Antes de finalizar um documento Markdown, verificar:

- Hierarquia correta de títulos
- Sintaxe consistente
- Blocos de código bem delimitados
- Links válidos
- Legibilidade em texto puro

Se algum item falhar, o documento deve ser ajustado.

## 17. Conflito e Hierarquia de Regras

Em caso de conflito, prevalece a seguinte ordem:

1. Canônico Global
2. Canônico de Domínio
3. Canônico de Formato Markdown
4. Comando específico

## 18. Regra de Evolução

Este canônico:

- Deve ser versionado
- Deve evoluir conforme práticas consolidadas da comunidade Markdown
- Não deve ser alterado para atender casos pontuais

## 19. Declaração Final

Este documento define o padrão oficial de formatação Markdown.
Qualquer documento em Markdown que não respeite estas regras deve ser considerado fora do padrão, independentemente da qualidade do conteúdo.