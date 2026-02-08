---
canonical: true
id: db-canon
title: "Canônico de Documentação — Banco de Dados"
inherits_from: production-dev-documentation-canon
version: "1.0"
date: "2026-02-08"
description: "Regras canônicas para documentação de banco de dados: modelagem, migrations, backups, operações." 
---

# Canônico — Banco de Dados

## Objetivo
Documentar modelo, operações, estratégias de backup/restore e políticas de manutenção do(s) banco(s) utilizados pelo projeto.

## Estrutura mínima
- Front matter com metadados.
- Desenho do modelo lógico e físico (ERD) e arquivo editável.
- Políticas de migrations e versionamento (ex.: ferramenta e convenções).
- Estratégia de backup/restore e RTO/RPO alvo.
- Índices críticos, partições, sharding e considerações de performance.
- Procedimentos operacionais (vacuum, compact, rebuild indexes) e janela de manutenção.

## Regras de conteúdo
- Incluir exemplos de queries de manutenção e de diagnóstico.
- Documentar contratos de dados entre serviços (formatos, constraints, events).
- Especificar políticas de retenção e GDPR/privacidade relacionadas a dados.

## Validação
- Migrations testadas em pipeline; backups validados regularmente e documented restore test.
