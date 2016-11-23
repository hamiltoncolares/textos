# Como organizo meu processo

## Processo

Meu processo de trabalho é estabelecido com base nos ensinamentos do mestre, [Rodrigo Yoshima][87eb0d55], que recebi em um curso Kanban. Para implementar o que aprendi com ele, e seguindo uma de suas orientações que dizia "Comece com o que você já tem", aproveitei a estrutura que minha equipe já e o fato de já usarmos o Trello. Nosso quadro é dividido da seguinte maneira:

- **Colunas:** Organizam o fluxo de execução das atividades (tarefas)

  - **Backlog:** Todas as tarefas que time já conhece e que ainda não planejamos a execução;
  - **Sprint:** Tarefas que estão prontas para serem executadas;
  - **Doing:** Tarefas que estão em execução nesse momento;
  - **Done:** Tarefas prontas que ainda não foram para produção;
  - **Teste:** Tarefas entregues pelo time de desenvolvimento para teste (Se você não tem pessoas separadas para teste, reavalie o uso dessa coluna. Ela também pode ser trocada por um _label_)
  - **Travamento:** Tarefas que, por qualquer motivo, foram planejadas, mas estão impedidas de continuar sua execução nesse momento;
  - **Produção:** Tarefas que já foram publicadas para o cliente final.

- **Labels:** Ajudam a identificar quais tipos de atividades estão sendo executadas

  - **Arquitetura:** Desenvolvimento, organização ou melhoria na arquitetura do produto;
  - **Funcionalidade:** Funcionalidade do produto;
  - **Bug:** Bugs a serem corrigidos;
  - **Crítica:** Tarefas de criticidade alta que devem ser tratadas de maneira diferenciada e com prioridade. Esse _label_, na maioria dos casos, é inserido em conjunto a um dos outros acima.

Toda Segunda-Feira (**impreterivelmente**), fazemos uma reunião de _replanishing_. Nessa reunião, que deve durar no máximo 20 minutos, discutimos em time quais atividades vamos executar durante a semana. Discutimos as prioridades, e aquilo que entedemos trará mais ganho para o cliente. O ideal é que alguém com ótima visão e entendimento da necessidade do cliente possa estar presente nessa reunião. Em alguns casos, o próprio cliente deve estar junto (quem melhor do que ele para saber o que mais o interessa?). As atividades que entedemos que conseguimos realizar durante a semana são movidas do _Backlog_ para o _Sprint_. O time fica livre para iniciar as atividades que estão no _Sprint_ a medida que tem condições de executar. Uma dúvida que sempre surge é: Mas e se surgir uma demanda de última hora que não está no _Sprint_? Essas são, geralmente, as críticas. Chegam a qualquer momento e passam por cima das outras. Se ela não precisa ser iniciada já e pode ficar para o próximo _replanishing_, é por que não é tão crítica assim e vai ficar no fluxo normal de execução, apenas com um nível alto de prioridade (colocamos sempre as mais prioritárias no topo da coluna). Na execução, os cards navegam pelo quadro conforme o fluxo descrito na explicação que dei das colunas. Não há muito segredo ou novidade quanto a isso.

## Métricas

Também mencionei que extraia métricas dos meus projetos, certo? É aí que entram [IFTTT][2143131e] e [Google Sheets][fffe8b33]. Infelizmente, esse processo ainda requer um trabalho manual que eu gostaria de automatizar, mas ainda não encontrei como.

### Coleta de dados

Para cada coluna do Trello, você deverá criar uma receita no IFTTT que inclui uma linha em uma planilha do Google com as seguintes informações do _Card_:

- Data
- Assunto
- Descrição
- Etapa
- Board
- Dono
- Link

![Planilha de informações do Trello](http://d.pr/i/F93g) ![Tabela de dados](http://d.pr/i/181re)

Aqui vem o primeiro processo manual. Para gerar os gráficos com métricas, a primeira solução que montei vai exigir que você crie uma nova aba para onde você leva as linhas inseridas automaticamente pelo _IFTTT_ de maneira organizada. Copio para essa planilha todas as novas atividades que entram em Sprint e nela crio colunas com os nomes das outras colunas por onde as atividades vão navegar. Sempre que um card é alterado, uma nova linha é criada na planilha inicial, nesse momento, vou até a aba que tem os dados organizados e incluo apenas a data em que o card entrou naquela coluna. Com essa atividade manual, posso automatizar em colunas paralelas, o tempo que cada atividade levou para sair de uma coluna para outra. Basta subtrair uma data da outra.

### Métricas

O que, de fato, nos interessa como métrica é o tempo que uma atividade leva para ser executada. Então, carrego da planilha de dados organizados as informações para uma tabela como a que está abaixo:

Nessa tabela temos as seguintes informações:

- **Backlog:** Quantidade de atividades não planejadas e que ainda estão por fazer. Corresponde à todas atividades que estão na coluna _Backlog_;
- **WIP:** Quer dizer: _Work In Progress_. Ou seja, quantidade de atividades que estão em execução. Corresponde à quantidade de atividades que estão nas colunas: _Sprint_, _Doing_, _Done_, _Teste_ e _Travamento_;
- **Done:** Atividades prontas que ainda não foram para produção. Corresponde à coluna _Done_;
- **Em produção:** Tudo que já está publicado em produção. Corresponde à coluna _Produção_.

Esse trabalho me permite ter, no mínimo os seguintes gráficos e informações (explicadas de maneira simplificada):

- **Lead:** Quanto tempo levo para colocar uma tarefa em produção;
- **Throughput:** Quantas tarefas consigo entregar em um determinado ciclo de tempo (usamos 1 semana como ciclo);
- **Cummulative Flow:** Qual a progressão do trabalho, considerando uma comparação entre as quantidades de tarefas que temos em _Backlog_, _WIP_ e _Produção_, dentro de um ciclo.

![Lead](http://d.pr/i/19I8j) ![Throughput](http://d.pr/i/14xb4) ![Cummulative Flow](http://d.pr/i/10hMq)

## Conclusão

Juntando uma análise dos seus gráficos, você poderá planejar com seu time o quanto você entrega e dizer para o seu cliente quando você vai entregar determinado grupo de funcionalidades a ele. Esse processo requer que você faça analises constantes para poder melhorar seu fluxo. Por outro lado, ele te dá dados reais do que está acontecendo. Há muito mais por trás do que está escrito aqui, mas aí vamos entrar em uma discussão de métodos e formas de trabalho que é bem longa. Eu estou muito com o Henrique, antes de qualquer coisa, mantenha seu fluxo simples (KIS). Eu uso o que te mostrei por que preciso levar report para gerência, preciso otimizar o trabalho do meu time, ... No fundo, o processo da maneira que mostrei aqui faz muito mais sentido pra mim do que outros métodos mais tradicionais que já usei. Bom, espero que tenha tido paciência para ler tudo. É certo que eu esqueci de dizer um monte de coisas importantes e que você vai ter dúvidas sobre toda essa coisa aí que escrevi. Fique à vontade para questionar, falar mal e, principalmente, sugerir coisas diferentes. Vou curitr muito ver gente criticando o que eu faço. Espero ter ajudado em algo!! :)

[2143131e]: https://ifttt.com/ "IFTTT"
[87eb0d55]: http://twitter.com/rodrigoy "Twitter"
[fffe8b33]: https://docs.google.com/spreadsheets/ "Google Sheets"
