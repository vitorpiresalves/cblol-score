# Dashboard — cblol-score

Visualização interativa dos scores calculados pelo notebook, construída no Power BI. O dashboard é composto por uma única página com filtro de posição, permitindo navegar entre as roles e comparar jogadores e times.

## Estrutura

O dashboard tem quatro elementos principais:

**Filtro de posição** — seleciona a role para filtrar todos os visuais da página simultaneamente. Ao selecionar uma posição, o Team Ranking, o Score Final e os cartões se atualizam para mostrar apenas os dados daquela role.

**Cartões de score médio** — exibem a média de GeralScore, AnchorScore, ConsistencyScore e CarryScore dos jogadores filtrados. As cores dos números indicam se a média está acima da média da role (verde), próxima (laranja) ou abaixo (vermelho).

**Team Ranking** — ranking dos times baseado na média do Score Final dos jogadores de cada time, filtrado pela posição selecionada. Mostra como cada organização se sai em cada role específica.

**Score Final** — ranking individual dos jogadores da posição selecionada, ordenado pelo Score Final de 50 a 100. A linha pontilhada verde representa a média da role.

## Prints

### Visão geral
`1dashboardpreview.png` — visão completa sem filtro de posição, mostrando todos os jogadores e o ranking geral de times.

### Top
`top.png` — filtro aplicado nos toplaners. RED Canids, LOUD e LØS lideram o Team Ranking pela posição. fNb, xyno e Zest aparecem no topo do Score Final.

### Jungle
`jungle.png` — filtro aplicado nos junglers. FURIA domina o Team Ranking com score, puxado pelo desempenho de Tatu, que aparece isolado no topo do Score Final muito acima dos demais.

`tatujng.png` — destaque individual de Tatu com todos os cartões em verde, evidenciando que ele está acima da média da role em todos os scores simultaneamente.

### Mid
`mid.png` — filtro aplicado nos midlaners. RED Canids lidera o Team Ranking. Kaze e Tutsz lideram o Score Final.

`midcomparativo.png` — comparativo que evidencia a mudança de roster da LOUD no meio do campeonato. Envy, que assumiu a vaga, terminou com score médio superior ao de Mago, seu antecessor, aparecendo rankeado acima dele no Score Final.

### Bot
`bot.png` — filtro aplicado nos atiradores. RED Canids e FURIA empatam no Team Ranking. Trigger, Rabelo e Ayu lideram o Score Final.

### Support
`sup.png` — filtro aplicado nos suportes. FURIA e RED Canids lideram o Team Ranking. JoJo e frosty aparecem no topo do Score Final.

## Observação
Os cálculos foram realizados antes da grande final, considerando os jogos disputados até 22 de fevereiro de 2026.

## Contato

**Vitor Fernando Pires Alves**  
- **Email:** vitor.fpiresalves@gmail.com
- **LinkedIn:** [linkedin.com/in/vitor-pires-alves](https://www.linkedin.com/in/vitor-pires-alves/)
