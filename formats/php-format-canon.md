---
canonical: true
id: php-format-canon
title: "Canônico de Formatação PHP"
scope: "formatação de arquivos PHP"
priority: "medium"
version: "1.0"
date: "2026-02-08"
inherits_from: global-canon
description: "Regras canônicas para escrita, estilo, segurança e validação de código PHP; segue o Canônico Global em caso de conflito."
---

# Canônico de Formatação PHP

## 1. Finalidade

Este documento define regras canônicas obrigatórias para desenvolvimento em PHP neste repositório: estilo, organização de código, validações, segurança e práticas de qualidade.

## 2. Princípios Gerais

- Seguir o Canônico Global em caso de conflito.
- Priorizar legibilidade, manutenção e segurança.
- Preferir código explícito, testável e com tipagem clara (onde aplicável).

## 3. Regras de sintaxe e arquivo

- Declarar strict types quando aplicável no topo dos arquivos:

```php
<?php
declare(strict_types=1);
```

- Arquivos PHP devem utilizar UTF-8 sem BOM.
- Espaçamento: 4 espaços para indentação (PSR-12 padrão).
- Fim de arquivo com nova linha.

## 4. Convenções de nomenclatura

- Namespaces e classes em StudlyCaps (PSR).
- Métodos e variáveis em camelCase.
- Constantes em UPPER_SNAKE_CASE.
- Arquivos correspondentes à classe: `App/Service/MyService.php` para `MyService`.

## 5. Estilo e padrões recomendados

- Seguir PSR-1 / PSR-12 para estilo de código.
- Organizar `use` statements em ordem alfabética e separados por uma linha entre blocos de grupos.
- Evitar uso excessivo de funções globais; preferir métodos em classes e injeção de dependência.
- Tipagem: adicionar type hints para parâmetros e retornos sempre que possível.

Exemplo:

```php
namespace App\Service;

class UserService
{
    public function getUserById(int $id): ?User
    {
        // ...
    }
}
```

## 6. Erros e exceções

- Preferir lançar exceções específicas ao invés de retornar valores de erro ambíguos.
- Não suprimir exceções silenciosamente; registrar e tratar adequadamente.

## 7. Segurança

- Nunca armazenar segredos em código; usar variáveis de ambiente.
- Sanitizar e validar entradas antes do uso (especialmente antes de consultas DB, execução de comandos ou inclusão de arquivos).
- Evitar `eval`, `exec` e funções similares; se estritamente necessário, justificar e isolar o uso.
- Preparar queries com prepared statements (PDO) ou ORM seguro para prevenir SQL Injection.

## 8. Dependências e Composer

- Usar Composer para gerenciamento de dependências.
- Preferir versões estáveis e auditar dependências por vulnerabilidades.

Exemplo mínimo `composer.json`:

```json
{
  "name": "vendor/project",
  "type": "project",
  "require": {
    "php": ">=8.0"
  },
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

## 9. Testes e qualidade

- Escrever testes automatizados (PHPUnit / Pest) para lógica crítica.
- Cobertura obrigatória para regras de negócio críticas (definir meta com o time).
- Integrar análise estática (PHPStan/psalm) e linter (PHP_CodeSniffer) no CI.

## 10. Linters e ferramentas sugeridas

- PHP_CodeSniffer (psr12) para style: configurar `phpcs --standard=PSR12`.
- PHPStan (nível 7-8 para rigor) ou Psalm para análise estática.
- Composer scripts recomendados:

```json
{
  "scripts": {
    "lint:php": "phpcs --standard=PSR12 src/",
    "analyse": "phpstan analyse src --level=7",
    "test": "phpunit"
  }
}
```

## 11. Estrutura de projeto recomendada

- `src/` — código fonte
- `tests/` — testes automatizados
- `config/` — arquivos de configuração
- `public/` — ponto de entrada web (index.php)

## 12. Versionamento e migrações

- Alterações de API públicas devem seguir versionamento semântico e ser documentadas.
- Para mudanças em banco de dados, usar migrações versionadas (ex.: Phinx, Doctrine Migrations).

## 13. Documentação

- Documentar APIs públicas com OpenAPI/Swagger quando aplicável.
- Comentar trechos complexos com PHPDoc e anotações de tipo.

## 14. Regras de conflito e evolução

1. Canônico Global
2. Canônico de Domínio
3. Canônico de Formato PHP (este documento)
4. Comando específico

Alterações no canônico devem ser deliberadas e versionadas.

## 15. Declaração Final

Este documento define o padrão oficial de desenvolvimento PHP para este repositório. Código que não obedecer estas regras deve ser ajustado para estar em conformidade.
