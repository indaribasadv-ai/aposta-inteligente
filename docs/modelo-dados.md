# Modelo de Dados – Aposta Inteligente

## Entidade: Modalidade
- id
- nome (Mega-Sena, Lotofácil, etc.)
- numero_minimo
- numero_maximo
- intervalo_inicio
- intervalo_fim
- possui_trevos (sim/não)
- quantidade_trevos (se aplicável)

## Entidade: Concurso
- id
- modalidade_id
- data_sorteio
- numeros_sorteados
- trevos_sorteados (se houver)

## Entidade: EstatisticaNumero
- id
- modalidade_id
- numero
- frequencia_60_meses
- ultima_aparicao

## Entidade: Simulacao
- id
- modalidade_id
- tipo_simulacao (mais_frequentes | menos_frequentes | misto)
- numeros_gerados
- data_simulacao

## Entidade: Usuario
- id
- email
- data_cadastro

## Entidade: Pagamento
- id
- usuario_id
- valor
- tipo (avulso)
- status (pago | pendente)
- data_pagamento
