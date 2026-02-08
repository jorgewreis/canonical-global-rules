---
canonical: true
id: js-format-canon
title: "Canônico de Formatação JavaScript"
scope: "formatação de arquivos JavaScript"
priority: "medium"
version: "1.0"
date: "2026-02-08"
inherits_from: global-canon
description: "Regras canônicas para formatação JavaScript; segue o Canônico Global em caso de conflito."
---

# Canônico de Formatação JavaScript

## 1. Finalidade

Este documento define regras canônicas obrigatórias para escrita, estilo e organização de código JavaScript neste repositório. Aplica-se a código frontend e Node.js, exceto quando regras de domínio especificarem outra coisa.

## 2. Princípios Gerais

- Seguir o Canônico Global em caso de conflito.
- Priorizar legibilidade, segurança e testabilidade.
- Preferir APIs explícitas e evitar comportamentos implícitos.

## 3. Ambiente e compatibilidade

- Escrever código em ECMAScript moderno (ES2020+) quando o ambiente suportar; fornecer transpile quando necessário.
- Usar módulos ES (`import` / `export`) por padrão.

## 4. Convenções de estilo

- Indentação: 2 espaços.
- Uso de `const` / `let`; evitar `var`.
- Preferir funções nomeadas para exportações públicas.
- Semicolons: usar semicolons (padrão do projeto).
- Nomes de variáveis e funções em camelCase; constantes em UPPER_SNAKE_CASE quando aplicável.

## 5. Arquitetura e organização de arquivos

- Agrupar funcionalidades em módulos pequenos e coesos.
- Evitar módulos com responsabilidade excessiva (SRP).
- Nomear arquivos com kebab-case em inglês (ex.: `user-service.js`) ou conforme convenção do projeto.

## 6. Segurança

- Validar e sanitizar entradas externas (requests, DOM, etc.).
- Evitar eval e construções dinâmicas.
- Tratar erros e não ocultar exceções sem justificativa.

## 7. Testes e qualidade

- Cobertura de testes automatizados para componentes críticos e lógicas de negócio.
- Usar linters (ESLint) com configuração compartilhada do projeto.
- Incluir testes unitários e, quando aplicável, testes de integração.

## 8. Assíncrono e promessas

- Preferir `async/await` sobre `then/catch` para legibilidade.
- Sempre tratar exceções em código assíncrono com `try/catch`.

## 9. Documentação e comentários

- Documentar APIs públicas com JSDoc ou formato equivalente.
- Comentar blocos complexos com explicação do porquê, não só o quê.

## 10. Dependências

- Preferir dependências leves e maduras.
- Manter atualizações regulares e auditar dependências por vulnerabilidades.

## 11. Performance

- Evitar operações síncronas custosas no loop principal (Node/event loop ou thread UI).
- Debounce/throttle em handlers de UI quando necessário.

## 12. Ferramentas e lint

- Usar `ESLint` com regras do projeto; integrar no CI.
- Usar `prettier` para formatação automática, sincronizado com ESLint quando necessário.

## 13. Exemplos comuns

Exemplo de módulo exportando função assíncrona:

```javascript
export async function fetchData(url) {
	const res = await fetch(url);
	if (!res.ok) throw new Error('Fetch failed');
	return res.json();
}
```

## 14. Regras de conflito e evolução

1. Canônico Global
2. Canônico de Domínio
3. Canônico de Formato JavaScript (este documento)
4. Comando específico

Alterações ao canônico devem ser deliberadas e versionadas.

## 15. Declaração Final

Este documento define o padrão oficial de formatação e práticas para JavaScript neste repositório.
