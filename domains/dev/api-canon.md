---
canonical: true
id: api-canon
title: "Canônico de Documentação — API & Contratos"
inherits_from: production-dev-documentation-canon
version: "1.0"
date: "2026-02-08"
description: "Regras canônicas para documentação de APIs: contratos, autenticação, exemplos e OpenAPI." 
---

# Canônico — API & Contratos

## Objetivo
Padronizar a documentação de APIs (REST/GraphQL) incluindo contrato, autenticação, exemplos e testes de integração.

## Estrutura mínima
- Front matter com metadados.
- Descrição do contrato: endpoints, métodos, parâmetros, status codes.
- Esquema de autenticação e autorização (JWT/OAuth2/scopes).
- Exemplos de request/response e coleções (Postman/Insomnia/HTTPie snippets).
- OpenAPI/Swagger spec (arquivo `openapi.yaml` na pasta do documento) ou link para schema.
- Política de versionamento da API.

## Regras de conteúdo
- Fornecer exemplos válidos e mocks para testes automatizados.
- Definir limites e SLAs, mensagens de erro padronizadas.
- Indicar mudanças retrocompatíveis e breaking changes no changelog da API.

## Validação
- Validar spec com ferramentas (openapi-validator) e gerar mocks/tests automaticamente quando possível.
