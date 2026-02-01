# Fonte de Dados (Oficial) + Pipeline

## Objetivo
Manter a base de concursos atualizada e calcular frequências dos últimos 60 meses por modalidade.

## Fonte de dados
Usar dados públicos/abertos (concursos e resultados) para cada modalidade.

## Pipeline (passos)
1) Baixar resultados por modalidade (lista de concursos)
2) Normalizar para um formato único (id, data, números, extras como “trevos” quando existir)
3) Guardar no banco (Concursos)
4) Rodar cálculo estatístico:
   - frequência por número nos últimos 60 meses
   - última aparição de cada número
5) Disponibilizar via API:
   - /modalidades
   - /estatisticas?modalidade=...
   - /simular (mais_frequentes | menos_frequentes | misto)
