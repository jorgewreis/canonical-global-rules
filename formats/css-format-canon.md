---
canonical: true
id: css-format-canon
title: "Canônico de Formatação CSS"
scope: "formatação de arquivos CSS"
priority: "medium"
version: "1.0"
date: "2026-02-08"
inherits_from: global-canon
description: "Regras canônicas para formatação CSS; segue o Canônico Global em caso de conflito."
---

# Canônico de Formatação CSS

## 1. Finalidade

Este documento define regras canônicas obrigatórias para a criação e formatação de arquivos CSS (inclui CSS puro, pré-processadores e CSS-in-JS quando aplicável). Foca em consistência, legibilidade, performance e acessibilidade.

## 2. Princípios Gerais

- Seguir o Canônico Global em caso de conflito.
- Priorizar consistência, clareza e previsibilidade sobre variações estilísticas.
- Preferir performance e manutenção preventiva (arquitetura CSS, cache, tamanho).

## 3. Estrutura e organização de arquivos

- Separar estilos por responsabilidade: `base/` (reset/normalize), `tokens/` (variáveis), `layout/`, `components/`, `pages/`, `utilities/`.
- Usar uma folha de estilo raiz que importe módulos numa ordem previsível.
- Evitar arquivos CSS monolíticos muito grandes — modularize por componente.

## 4. Variáveis e tokens

- Preferir CSS Custom Properties (`--nome`) para theming e variáveis runtime quando possível.
- Para pré-processadores, alinhar nomes com a convenção de tokens do projeto.
- Definir tokens em `:root` ou arquivo `tokens.css` com comentários explicativos.

Exemplo:

```css
:root {
	--color-primary: #0b5fff;
	--space-1: 4px;
}
```

## 5. Convenções de sintaxe e estilo

- Indentação: 2 espaços por nível.
- Separador entre regras: uma linha em branco entre blocos conceituais.
- Uso de minúsculas para propriedades e nomes de classes (`.btn-primary`).
- Preferir classes sem depender de IDs para estilo.
- Evitar `!important` salvo justificativa documentada.

## 6. Organização de seletores e especificidade

- Prefira seletividade baixa e previsível (classes) e evite seletores encadeados profundos.
- Use BEM ou convenção de nomenclatura aprovada pelo projeto para componentes complexos.
- Em geral, evitar seletores de atributo e tag para regras complexas.

## 7. Responsabilidade e escopo

- Cada componente deve ter escopo claro (namespace de classes) e não vazar estilos globais.
- Utilitários (`.u-...` ou `.is-...`) são permitidos para casos de layout genéricos.

## 8. Performance e build

- Remover CSS não utilizado no processo de build (purgecss, etc.).
- Minificar e concatenar conforme pipeline de build.
- Evitar regras CSS que forcem repaints/reflows frequentes (ex.: usar transform/opacity para animações quando possível).

## 9. Acessibilidade (a11y)

- Garantir contraste suficiente para texto (seguir WCAG AA mínimo).
- Respeitar preferências do usuário: `prefers-reduced-motion`, `prefers-contrast`.
- Evitar esconder conteúdo somente com `display:none` se precisar ser acessível a leitores de tela.

## 10. Animações e transições

- Preferir transições suaves e limitar propriedades animadas (transform, opacity).
- Fornecer alternativa para usuários que reduzam animação via `@media (prefers-reduced-motion: reduce)`.

## 11. Comentários e documentação

- Comentar trechos complexos com `/* ... */` e incluir rationale quando usar hacks.
- Manter um changelog de tokens/variáveis quando alterados.

## 12. Ferramentas e lint

- Recomenda-se usar `stylelint` com configuração compartilhada do projeto para aplicar regras automáticas.
- Integrar verificação no CI (lint e build) antes de mesclar.

## 13. Exemplos comuns

Exemplo de componente:

```css
.card {
	display: block;
	padding: var(--space-3);
	background: var(--color-surface, #fff);
}
```

## 14. Regras de conflito e evolução

1. Canônico Global
2. Canônico de Domínio
3. Canônico de Formato CSS (este documento)
4. Comando específico

O canônico deve ser versionado e alterado apenas deliberadamente.

## 15. Declaração Final

Este documento define o padrão oficial de formatação CSS para este repositório. Arquivos que não obedecerem estas regras devem ser ajustados.
