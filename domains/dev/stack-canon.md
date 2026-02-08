---
canonical: true
id: stack-canon
title: "Canônico de Documentação — Stack Técnica"
inherits_from: production-dev-documentation-canon
version: "1.0"
date: "2026-02-08"
description: "Regras canônicas para documentos que descrevem a stack tecnológica e infra (versões, rationale, deploy)."
---

# Canônico — Visão Técnica / Stack

## Objetivo
Padronizar a documentação da stack tecnológica (frontend, backend, banco, cache, mensageria, infra) incluindo versões, escolhas, e estratégias de deploy.

## Estrutura mínima
- Front matter com metadados obrigatórios.
- Lista das tecnologias principais com versões e rationale (por que escolhidas).
- Diagramas de integração com dependências externas.
- Estratégia de ambientes (dev/staging/prod) e pipelines CI/CD.
- Matrizes de compatibilidade e requisitos mínimos de runtime.
- Instruções de rollback e estratégia de releases.

## Regras de conteúdo
- Sempre justificar escolhas com alternativas consideradas.
- Incluir comandos de setup e links para repositórios/artefatos relevantes.
- Indicar responsáveis (owners) por cada componente.

## Validação
- Validar que versões e comandos funcionam em ambiente de build (CI) e atualizar quando pipelines mudarem.
