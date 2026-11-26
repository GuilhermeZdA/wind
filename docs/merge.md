# Merge na main

O merge só pode ser feito quando **todas** as condições forem atendidas:

* ✅ CI executou e está **verde**.
* ✅ Há **pelo menos 1 aprovação** de alguém que não escreveu o código (2 em caso de dúvida).
* ✅ Todos os comentários foram resolvidos.
* ✅ A branch está atualizada com a `main` e sem conflitos.

## Como fazer

* Use **Squash and merge**, mantendo o histórico da `main` limpo. O título do commit segue o padrão Conventional Commits.
* Após o merge, **delete a branch** (remota e local).
* Confirme que a issue foi fechada e o cartão foi para **Concluído**.

```bash
git checkout main
git pull origin main
git branch -d feat/12-classe-conta-bancaria
```

## Regras

* Ninguém faz push direto na `main`.
* Nunca use `push --force` na `main`.
* Quem abriu o PR não aprova o próprio PR.

## Quando o CI quebra na `main`

Quem corrige depende da **gravidade**, da **complexidade** e da **urgência**:

* **Quem fez o push** é o primeiro a ser chamado, pois conhece a mudança.
* Se estiver indisponível ou a correção for complexa, **qualquer outra pessoa da equipe** pode assumir.
* Avise a equipe **imediatamente** no canal combinado.
* Se a `main` quebrada está **bloqueando o trabalho de todos**, a correção passa na frente das outras tarefas.
* A correção também entra por **PR** (por exemplo `fix/...`). Se for mais rápido, faça um **revert** do PR problemático e corrija com calma depois.
* Marque o cartão com a label `bloqueada` se algo ficar impedido por causa disso.