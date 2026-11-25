# Scrumban

Usamos um **Scrumban leve**: a cadência de sprints do Scrum (planejamento, daily, review) combinada com o quadro e o fluxo puxado do Kanban. Não há Scrum Master nem Product Owner fixos. A equipe toda assume esses papéis em conjunto, e os requisitos são definidos por nós mesmos.

## Quadro

Ferramenta: **GitHub Projects**. Cada issue vira um cartão.

| Coluna | O que significa | Quando o cartão entra |
| :--- | :--- | :--- |
| **Backlog** | Todas as ideias e tarefas, ordenadas por prioridade (MoSCoW) | Issue criada |
| **Pronto para fazer** (To Do) | Tarefa que cumpre a [Definition of Ready](issues.md#definition-of-ready) e foi escolhida na Planning | Definida na Planning |
| **Em andamento** | Alguém está trabalhando: branch criada, ciclo de [TDD](tdd.md) rodando | A pessoa puxa o cartão |
| **Em revisão** | PR aberto, CI rodando e aguardando review | PR aberto |
| **Concluído** | PR mergeado e [Definition of Done](definition-of-done.md) atendida | Merge na `main` |

## Regras do fluxo

### Puxar tarefas
* Cada pessoa **puxa** sozinha uma tarefa da coluna *Pronto para fazer*. Ninguém atribui tarefa para outra pessoa.
* Ao puxar, a pessoa se atribui como **assignee** na issue e cria a branch.
* Se alguém quiser uma tarefa que **já está com outra pessoa**, deve perguntar a ela e combinar a divisão do trabalho antes de mexer.

### Limite de trabalho em andamento (WIP)
* **No máximo 2 cartões por pessoa** na coluna *Em andamento*.
* Antes de puxar uma tarefa nova, tente destravar o que já está em *Em revisão*: revisar o PR de um colega vale mais do que começar algo novo.

### Tarefas bloqueadas
* Não existe coluna de bloqueio. Use a label **`bloqueada`** no cartão.
* Ao marcar, escreva um comentário na issue explicando **o motivo** e **o que precisa acontecer** para destravar.
* Avise a equipe na próxima daily (ou antes, se estiver travando outras pessoas).
* Remova a label assim que o bloqueio acabar.

### Prioridade (MoSCoW)
A prioridade é definida **em reunião**, com a equipe agindo como Product Owner:

| Categoria | Significado |
| :--- | :--- |
| **Must have** | Essencial. Sem isso o projeto não funciona ou não atende aos requisitos |
| **Should have** | Importante, mas há alternativa temporária |
| **Could have** | Desejável, entra se sobrar tempo |
| **Won't have (agora)** | Fica fora desta etapa do projeto |

A **ordem das issues no Backlog** reflete a prioridade: o que está mais acima é o que deve ser puxado primeiro.

### Tamanho das tarefas
* Não fazemos estimativa formal (sem story points ou P/M/G).
* Cada issue deve ser **pequena o bastante para caber em poucos dias**. Se estiver grande, quebre em issues menores.

## Como medimos o andamento

* **Cartões concluídos** por sprint (métrica principal).
* Opcionalmente, olhar o "peso" do cartão de forma informal (ex: tarefa grande ou pequena) ao conversar sobre a sprint. Não há estimativa numérica.

## Cerimônias

Planning, daily, review e retrospectiva estão em [cerimonias.md](cerimonias.md).