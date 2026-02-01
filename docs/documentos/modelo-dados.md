# Modelo de Dados — Aposta Inteligente

Este documento descreve o modelo lógico inicial de dados do aplicativo.

## Entidades principais

### Usuário
- id
- nome
- email
- data_criacao

### Simulação
- id
- usuario_id
- modalidade (Mega-Sena, Lotofácil, Quina, Dupla Sena, +Milionária)
- quantidade_jogos
- data_simulacao

### JogoGerado
- id
- simulacao_id
- numeros_gerados
- criterio_estatistico_utilizado

### Pagamento
- id
- simulacao_id
- valor
- status
- data_pagamento
