# cblol-score

Sistema de análise e pontuação de performance de jogadores do CBLOL baseado em dados públicos do [Oracle Elixir](https://oracleselixir.com).

## Dados

Os dados utilizados são disponibilizados pelo Oracle Elixir, que coleta e organiza estatísticas de partidas profissionais de League of Legends. Baixe o CSV diretamente em [oracleselixir.com/tools/downloads](https://oracleselixir.com/tools/downloads).

## Métricas derivadas

Antes de calcular os scores, o notebook cria uma série de métricas a partir dos dados brutos:

**Delta Gold, XP e CS** — variação da diferença de gold, experiência e CS entre os intervalos de 10, 15, 20 e 25 minutos. Em vez de olhar o snapshot isolado de cada momento, o delta mostra o quanto o jogador ganhou ou perdeu de vantagem em cada intervalo, revelando padrões de domínio ou queda ao longo do tempo.

**Kill Participation (KP)** — percentual das kills do time em que o jogador participou, seja como kill ou assist. Mede o envolvimento do jogador nas ações ofensivas do time.

**Kill Share (KS%)** — percentual das kills do time que foram diretamente do jogador, sem contar assists. Complementa o KP mostrando quem finaliza as jogadas.

**Damage Efficiency** — relação entre o dano share e o gold share do jogador. Mede se o jogador entrega mais dano do que o proporcional aos recursos que recebe — quanto maior, mais eficiente ofensivamente com os recursos do time.

**Combat Efficiency** — combina DPM com kills, assists e mortes para medir o impacto geral em combate. Jogadores que causam muito dano e participam de muitas kills sem morrer muito têm combat efficiency alta.

## Scores

### Score Base

Mede a performance geral do jogador por partida. Para cada role, as features são ponderadas automaticamente pela correlação de Spearman com o resultado da partida, ou seja, as estatísticas que mais impactam vitórias na posição recebem mais peso. O score é calculado por jogo e depois agregado com peso maior para partidas de playoff.

Features utilizadas: gold diff, XP diff e CS diff nos intervalos de 10 a 25 minutos, eficiência de dano, eficiência de combate, kill participation, kill share, CSPM, VSPM e first blood.

### Anchor Score

Mede o quanto o jogador se destaca dentro do próprio time, ajustado pela força do time. Um jogador num time forte precisa se sobressair mais para ter um Anchor Score alto, evitando que jogadores medianos sejam inflados por estarem num time bom. Jogadores com poucos jogos são puxados para 0.5 para evitar distorções por amostra pequena.

### Carry Score

Mede a capacidade do jogador de converter recursos em vitória. A base é 0.5 e jogadores que não têm perfil de carry ficam próximos desse valor sem penalização. Quem recebe recursos acima da mediana da própria role, está na frente no gold diff e converte isso em vitória sobe acima de 0.5. Quem recebe recursos, está na frente e perde cai abaixo. O support é excluído desse score por não ter perfil de carry por recursos.

### Consistency Score

Mede a estabilidade de performance ao longo do split. Combina a média de score, o piso de performance (percentil 25) e a amplitude entre jogos bons e ruins. Um jogador consistente tem média alta, piso alto e pouca variação, o oposto de um jogador que alterna entre jogos muito bons e muito ruins.

### Score Final

Combinação dos três scores anteriores com pesos calculados automaticamente pela correlação de Spearman com vitória por role. O Anchor Score tem peso fixo de 5% no Score Final como ajuste contextual, enquanto os outros três dividem os 95% restantes conforme o peso calculado por posição.

## Observações

Os scores são relativos ao dataset utilizado e comparam jogadores dentro da mesma liga e split. Não é recomendado comparar scores entre ligas diferentes ou splits diferentes, pois patches e meta impactam diretamente as estatísticas.

## Contato

**Vitor Fernando Pires Alves**  
- **Email:** vitor.fpiresalves@gmail.com
- **LinkedIn:** [linkedin.com/in/vitor-pires-alves](https://www.linkedin.com/in/vitor-pires-alves/)
