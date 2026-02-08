---
canonical: true
id: html-format-canon
title: "Canônico de Formatação HTML"
scope: "formatação de arquivos HTML"
priority: "medium"
version: "1.0"
date: "2026-02-08"
inherits_from: global-canon
description: "Regras canônicas para formatação HTML; segue o Canônico Global em caso de conflito."
---

# Canônico de Formatação HTML

## 1. Finalidade

Este documento define regras canônicas obrigatórias para a formatação de artefatos HTML produzidos neste projeto. Trata exclusivamente de forma, sintaxe, semântica e requisitos de acessibilidade e portabilidade.

## 2. Princípios Gerais

- Obedecer ao Canônico Global em caso de conflito.
- Priorizar interoperabilidade (HTML5 / Common practices) e acessibilidade (WCAG).
- Ser legível em texto puro e organizado semanticamente.

## 3. Estrutura mínima e cabeçalho

- Incluir sempre a declaração do tipo de documento: `<!doctype html>`.
- Definir `lang` no elemento `<html lang="xx">`.
- Cabeçalho mínimo recomendado:

```html
<!doctype html>
<html lang="pt-BR">
	<head>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width,initial-scale=1">
		<title>Título da página</title>
	</head>
	<body>
		<!-- conteúdo -->
	</body>
</html>
```

## 4. Sintaxe e estilo

- Tags e atributos em minúsculas (`<header>`, `class`, `id`).
- Usar aspas duplas para valores de atributos: `class="exemplo"`.
- Indentação: 2 espaços por nível (consistente em todo o arquivo).
- Não usar barras de fechamento em elementos void (HTML5): use `<img src="..." alt="...">`, não `<img />`.

## 5. Ordem e convenções de atributos

Recomenda-se, quando aplicável, a seguinte ordem de atributos para legibilidade:

1. `id`
2. `class`
3. `data-*` attributes
4. `src` / `href`
5. `alt`, `title`
6. `role`, `aria-*`

Exemplo:

```html
<img id="logo" class="site-logo" src="/img/logo.png" alt="Logo do site" />
```

## 6. Acessibilidade (a11y)

- Sempre fornecer `alt` descritivo para imagens informativas.
- Para imagens decorativas, usar `alt=""` e considerar `role="presentation"` quando necessário.
- Elementos interativos devem ser acessíveis via teclado e ter atributos ARIA quando necessário (`aria-label`, `aria-hidden` etc.).
- Formulários: cada controle deve ter `<label for="id">` correspondente; use `fieldset`/`legend` quando apropriado.

## 7. Links e segurança

- Links externos que abrem em nova aba devem usar `rel="noopener noreferrer"` com `target="_blank"`.
- Preferir URLs completas para referências externas (incluir protocolo `https://`).

## 8. CSS e JavaScript

- Preferir CSS externo via `<link rel="stylesheet" href="...">` no `<head>`.
- Scripts devem ser carregados com `defer` no `<head>` ou colocados no final do `<body>` quando apropriado.
- Evitar estilos inline (`style="..."`) salvo necessidade explícita.

## 9. Comentários e conteúdo sensível

- Usar `<!-- comentário -->` para notas de implementação; nunca incluir segredos ou credenciais.

## 10. Tabelas e dados tabulares

- Usar `<table>` apenas para dados tabulares (não para layout).
- Incluir `<caption>` quando houver contexto; usar `<thead>`, `<tbody>`, `<th scope="col">` para acessibilidade.

## 11. Formulários

- Associar `label` a inputs via `for`/`id`.
- Usar tipos de input semânticos (`type="email"`, `type="tel"`, etc.).

## 12. Validação e testes

- Validar o HTML gerado com validadores oficiais (W3C Markup Validation Service) e ferramentas de acessibilidade (axe, Lighthouse).

## 13. Compatibilidade e Portabilidade

- Seguir HTML5 e evitar extensões proprietárias não amplamente suportadas.
- Manter o conteúdo funcional em navegadores modernos e degrade graciosamente quando necessário.

## 14. Regras de Conflito

Em caso de conflito entre regras, obedecer à ordem de precedência:

1. Canônico Global
2. Canônico de Domínio
3. Canônico de Formato (este documento)
4. Comando específico

## 15. Regra de Evolução

- O canônico deve ser versionado e alterado somente mediante deliberação.

## 16. Exemplos comuns

Exemplo de link externo seguro:

```html
<a href="https://exemplo.com" target="_blank" rel="noopener noreferrer">Visitar</a>
```

Exemplo de imagem acessível:

```html
<img src="/img/diagram.png" alt="Diagrama mostrando a arquitetura da solução">
```

## 17. Declaração Final

Este documento define o padrão oficial de formatação HTML para este projeto. Qualquer arquivo HTML que não respeite estas regras deve ser considerado fora do padrão até ser ajustado.
