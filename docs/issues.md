# Issues

Toda tarefa começa com uma issue. Ela é a fonte de verdade sobre o que precisa ser feito, e cada issue vira um cartão no quadro (veja [scrumban.md](scrumban.md)).

## Templates por tipo

As issues são mais **técnicas** (sem user stories) e seguem um template por tipo, que ficam em `.github/ISSUE_TEMPLATE/`:

| Template | Quando usar | Prefixo da branch |
| :--- | :--- | :--- |
| `feature` | Nova funcionalidade | `feat/` |
| `bug` | Correção de erro | `fix/` |
| `docs` | Documentação | `docs/` |
| `refactor` | Melhoria interna sem mudar o comportamento | `refactor/` |
| `test` | Criação ou ajuste de testes | `test/` |

Todos pedem a mesma base: **o que será feito** e **critérios de aceite**. Os critérios de aceite são a base dos testes do [TDD](tdd.md).

## Regras

* Uma issue = uma entrega pequena e focada.
* **Tamanho máximo:** deve caber em poucos dias. Se for maior, quebre em várias.
* Não há estimativa formal (sem story points).
* A **prioridade** vem da ordem no Backlog, definida em reunião com MoSCoW.
* Dúvidas e discussões sobre a tarefa ficam nos **comentários da issue**.
* Única label usada: **`bloqueada`**. Tipo e prioridade não usam label.

## Definition of Ready

Uma issue só vai para **Pronto para fazer** quando:

- [ ] Tem **critérios de aceite** claros.
- [ ] É **pequena o bastante** para caber em poucos dias.
- [ ] **Não depende de outra** issue ainda não concluída.

## Nome da branch com a issue

Além do padrão de prefixos do README principal, inclua o **número da issue** no nome da branch:

```text
tipo/numero-da-issue-descricao-curta
```

| Exemplo | Issue |
| :--- | :--- |
| `feat/12-classe-conta-bancaria` | #12 |
| `fix/25-erro-calculo-saldo` | #25 |
| `test/18-testes-validacao-cpf` | #18 |

```bash
git checkout main
git pull origin main
git checkout -b feat/12-classe-conta-bancaria
```