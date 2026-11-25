# Fluxo Completo de Desenvolvimento

Visão geral do caminho de uma tarefa, da ideia até a `main`. Trabalhamos com **Scrumban + TDD**.

```text
Issue (Backlog) → Pronto para fazer → Em andamento (branch + TDD) → Em revisão (PR + CI)
                → Aprovado → Merge na main → Concluído
```

## Passo a passo

| # | Etapa | Coluna do quadro | O que fazer | Detalhes |
| :-: | :--- | :--- | :--- | :--- |
| 1 | **Issue** | Backlog | Criar a issue usando o template do tipo da tarefa | [issues.md](issues.md) |
| 2 | **Planning** | Pronto para fazer | Priorizar (MoSCoW) e escolher o que entra na sprint | [cerimonias.md](cerimonias.md) |
| 3 | **Puxar a tarefa** | Em andamento | Atribuir a si mesmo (máx. 2 por pessoa) e criar a branch | [scrumban.md](scrumban.md) |
| 4 | **TDD** | Em andamento | Testes a partir dos critérios de aceite, código, refatoração | [tdd.md](tdd.md) |
| 5 | **Commit** | Em andamento | Commits pequenos no padrão Conventional Commits | README principal |
| 6 | **Push e PR** | Em revisão | Abrir o PR vinculando a issue | [pull-request-e-revisao.md](pull-request-e-revisao.md) |
| 7 | **CI** | Em revisão | Pipeline roda testes e cobertura automaticamente | [ci.md](ci.md) |
| 8 | **Revisão** | Em revisão | 1 aprovação de outra pessoa (2 em caso de dúvida) | [pull-request-e-revisao.md](pull-request-e-revisao.md#revisão-de-código) |
| 9 | **Merge** | Concluído | Só com CI verde e aprovação | [merge.md](merge.md) |
| 10 | **Review da sprint** | Concluído | Demonstrar o que foi entregue | [cerimonias.md](cerimonias.md) |

## Regras de ouro

* **Nada é feito sem uma issue.**
* **Ninguém faz push direto na `main`.** Todo código entra via Pull Request.
* **Testes primeiro (TDD)** é o padrão. Exceções precisam de justificativa.
* **No máximo 2 cartões por pessoa em andamento.**
* **A `main` só recebe código com CI verde e pelo menos 1 aprovação.**
* **Quem escreveu o código não aprova o próprio PR.**

## Outros documentos

* [scrumban.md](scrumban.md): quadro, colunas, WIP, MoSCoW.
* [cerimonias.md](cerimonias.md): planning, daily, review e retrospectiva.
* [definition-of-done.md](definition-of-done.md): quando uma tarefa está pronta.
* [boas-praticas-poo.md](boas-praticas-poo.md): princípios de POO e código limpo.
* [configuracao-repositorio.md](configuracao-repositorio.md): como tornar as regras obrigatórias no GitHub.