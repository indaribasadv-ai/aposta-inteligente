# Roadmap MVP — Aposta Inteligente

## Objetivo do MVP
Permitir ao usuário:
1) Escolher uma modalidade oficial
2) Definir quantidade de números (dentro da regra)
3) Gerar até 5 jogos por compra (R$ 9,95)
4) Ver análise estatística dos últimos 60 meses (mais/menos frequentes)
5) Baixar/visualizar os jogos gerados (para copiar e apostar por conta própria)

## Regras de produto (não negociáveis)
- O app NÃO faz aposta na Caixa.
- O app é uma simulação estatística, sem promessa de ganho.
- Limite: até 5 jogos por compra.
- Histórico de compras + reexibição dos jogos gerados (por 30 dias ou 90 dias — definir depois).

## Modalidades no MVP (fase 1)
Entram no MVP:
- Mega-Sena
- Lotofácil
- Quina
- Dupla Sena
- +Milionária

Ficam fora (fase 2):
- Loteca (depois)
- Outras (definir depois)

## Estratégias disponíveis (MVP)
- MAIS_FREQUENTES (60 meses)
- MENOS_FREQUENTES (60 meses)
- MISTO (50/50)
- ALEATORIO_CONTROLADO (ponderado)

## Telas do MVP
1) Tela Inicial
- Explicação rápida
- Botão “Começar”
- Aviso legal (sem garantia)

2) Seleção de Modalidade
- Lista das modalidades do MVP
- Link “regras da modalidade”

3) Configurar Simulação
- Quantidade de números
- Quantidade de jogos (1 a 5)
- Estratégia (mais/menos/misto/ponderado)

4) Pagamento (R$ 9,95)
- Pagar e liberar a geração
- Após pagamento aprovado → gerar jogos

5) Resultado
- Jogos gerados (cópia fácil)
- Estatísticas resumidas (ex.: % top, média frequência)
- Botão “Gerar novamente” (nova compra)
- Botão “Salvar/Exportar”

6) Histórico
- Lista das últimas simulações pagas
- Reabrir detalhes

## Dados mínimos (MVP)
- Usuario (ou ID anônimo)
- Compra (status, data, valor)
- Simulação (modalidade, parâmetros, jogos gerados)
- Frequências (cache por modalidade e período)

## Pagamento — decisão
Opção A (mais simples no Brasil):
- Mercado Pago (link de pagamento / checkout)
Opção B:
- Stripe (melhor fora do Brasil)

MVP recomendado: Mercado Pago.

## Checklist de entrega
- [ ] Regras por modalidade confirmadas no arquivo de regras
- [ ] Algoritmo documentado
- [ ] Roadmap MVP fechado
- [ ] Definição do stack (web primeiro)
- [ ] Protótipo de telas (simples)
- [ ] Integração pagamento
- [ ] Integração com base de resultados (60 meses)
