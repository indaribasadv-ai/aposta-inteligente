# Algoritmo de Simulação (Aposta Inteligente)

## Objetivo
Gerar combinações de apostas respeitando as regras oficiais de cada modalidade, com base em estatísticas dos últimos 60 meses.

## Entradas (inputs)
- modalidade: (ex.: Mega-Sena, Lotofácil, Quina, Dupla Sena, +Milionária etc.)
- qtd_numeros: quantidade de números que o usuário quer apostar (dentro do mínimo e máximo permitido)
- qtd_jogos: quantidade de jogos a gerar (limite: 1 a 5)
- estrategia:
  - MAIS_FREQUENTES
  - MENOS_FREQUENTES
  - MISTO (50/50)
  - ALEATORIO_CONTROLADO (ponderado pelas frequências)
- periodo_meses: padrão = 60

## Regras gerais (sempre)
1) Validar qtd_numeros dentro do permitido pela modalidade.
2) Validar qtd_jogos <= 5.
3) Não repetir número dentro do mesmo jogo.
4) (Opcional para evitar duplicidade) Evitar jogos idênticos entre si.
5) Se a modalidade tiver "extras" (ex.: trevos), tratar como campos separados com suas próprias regras.

## Base estatística
Para a modalidade selecionada, construir:
- lista_numeros_validos: ex.: 1..60 (Mega), 1..25 (Lotofácil), etc.
- freq[num]: contagem de vezes que o número saiu no período
- recencia[num]: quantos concursos desde a última aparição (quanto maior, mais “atrasado”)
- ordenar por freq:
  - ranking_mais = desc(freq)
  - ranking_menos = asc(freq)

## Estratégias de geração
### A) MAIS_FREQUENTES
- Selecionar um "pool" dos TOP X% números (ex.: top 40%).
- Sortear qtd_numeros dentro do pool, sem repetição.
- Se faltar número (pool pequeno), completar com próximos do ranking.

### B) MENOS_FREQUENTES
- Selecionar um "pool" dos BOTTOM X% números (ex.: bottom 40%).
- Sortear qtd_numeros dentro do pool, sem repetição.
- Se faltar número, completar com próximos do ranking.

### C) MISTO (50/50)
- Metade dos números vem do pool MAIS (top 40%)
- Metade vem do pool MENOS (bottom 40%)
- Se qtd_numeros for ímpar, colocar +1 no MAIS (por padrão).
- Sortear sem repetição, garantindo que não repita o mesmo número vindo dos dois pools.

### D) ALEATORIO_CONTROLADO (ponderado)
- Atribuir peso a cada número com base em freq (e opcionalmente recência).
  Ex.: peso = freq[num] + 1
- Sortear por roleta ponderada até completar qtd_numeros (sem repetição).
- Ajuste opcional: dar um bônus de peso para números “atrasados”:
  peso_final = (freq + 1) * (1 + recencia_norm)

## Anti-vício / Controle de repetição (recomendado)
Para reduzir jogos muito parecidos:
- Definir um limite de interseção entre jogos (ex.: no máximo 60% iguais).
- Se passar do limite, regenerar o jogo.

## Saídas (outputs)
Para cada jogo:
- modalidade
- numeros_escolhidos (ordenados)
- parametros usados (estrategia, periodo_meses, qtd_numeros)
- resumo estatístico (opcional):
  - média de frequência dos números do jogo
  - quantos números do top 20% entraram
  - quantos números “atrasados” entraram

## Aviso obrigatório ao usuário
- “Isto é uma simulação estatística baseada em resultados passados e não garante premiação.”
- “Aposta é um jogo de azar. Jogue com responsabilidade.”
