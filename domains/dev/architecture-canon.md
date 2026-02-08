---
canonical: true
id: architecture-canon
title: "Canônico de Documentação — Arquitetura"
inherits_from: production-dev-documentation-canon
version: "1.0"
date: "2026-02-08"
description: "Regras canônicas para documentos de Arquitetura de Sistema (visão, decisões, diagramas, ADRs)."
---

# Canônico — Arquitetura do Sistema

## Objetivo
Fornecer regras e estrutura mínima para documentos de arquitetura que descrevem componentes, responsabilidades, fluxos, deployment e decisões arquiteturais.

## Estrutura mínima obrigatória
- Front matter: `id`, `title`, `version`, `date`, `status`, `authors`.
- Sumário (TOC) quando o documento tiver mais que 3 seções.
- Visão geral: contexto, escopo e objetivos arquiteturais.
- Diagrama(s): componente, sequência e deployment (links para fontes editáveis + export PNG/SVG).
- Componentes e responsabilidades: descrição de cada peça (interface, dependências, SLAs).
- Requisitos não funcionais: disponibilidade, performance, escalabilidade, segurança.
- Decisões arquiteturais (resumo) e links para ADRs completas.
- Impactos e trade-offs assumidos.

## Requisitos de conteúdo e formato
- Diagrama em formato editável (draw.io / diagrams.net) no repositório e export em PNG/SVG.
- Uso de linguagem técnica objetiva; evitar termos vagos sem definição.
- Cada decisão relevante deve ter referência a um ADR no diretório `docs/architecture/adr/`.

## Validação e entrega
- Checklist de validação antes da entrega: diagramas presentes, ADRs referenciadas, requisitos não funcionais documentados, owners listados.

## Notas
- Atualizar document when changes that affect topology or SLAs occur.
