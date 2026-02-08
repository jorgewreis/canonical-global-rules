---
canonical: true
id: ops-canon
title: "Canônico de Documentação — Observabilidade & Operações"
inherits_from: production-dev-documentation-canon
version: "1.0"
date: "2026-02-08"
description: "Regras canônicas para documentação de observabilidade: métricas, logs, tracing, SLIs/SLOs e dashboards." 
---

# Canônico — Observabilidade e Operações

## Objetivo
Padronizar como documentar métricas, logs, tracing e práticas de operação para facilitar diagnóstico, SRE e SLA management.

## Estrutura mínima
- Front matter com metadados.
- Lista de métricas críticas (SLIs) e objetivos (SLOs) com targets mensuráveis.
- Logs: formato, campos obrigatórios e política de retenção.
- Tracing: conventions (trace ids), exemplos de spans e integração OpenTelemetry.
- Dashboards e alerting: links para dashboards e regras de alerta com severities e runbooks.

## Regras de conteúdo
- Cada alerta deve mapear para um runbook.
- Definir responsáveis por métricas e níveis de on-call.

## Validação
- Testar alertas e coverage de métricas em ambiente staging.
