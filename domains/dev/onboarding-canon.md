---
canonical: true
id: onboarding-canon
title: "Canônico de Documentação — Onboarding & Developer Experience"
inherits_from: production-dev-documentation-canon
version: "1.0"
date: "2026-02-08"
description: "Regras canônicas para documentação de onboarding, setup local, ferramentas e boas práticas para novos desenvolvedores." 
---

# Canônico — Onboarding e Developer Experience

## Objetivo
Documentar o processo de entrada de novos desenvolvedores, configuração do ambiente local e práticas que garantam produtividade inicial.

## Estrutura mínima
- Front matter com metadados.
- Passo-a-passo para configurar ambiente local (OS specifics, dependências, comandos).
- Comandos úteis: build, test, lint, run, debug.
- Documentação de acesso a recursos (VPN, secrets vault, credenciais de teste).
- Checklist de primeiro PR e expectativas de revisão.

## Regras de conteúdo
- Manter scripts de setup automatizados (ex.: `make setup`, `scripts/bootstrap`) quando possível.
- Indicar problemas conhecidos e soluções rápidas (FAQ).

## Validação
- Testar setup em máquina limpa periodicamente e atualizar scripts conforme mudanças.
