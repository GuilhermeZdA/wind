# Pull Request e Revisão de Código

Ao abrir o PR, o cartão vai para **Em revisão** no quadro.

## Antes de abrir o PR (checklist do autor)

* [ ] Todos os testes passam localmente.
* [ ] Existem testes cobrindo os critérios de aceite da issue.
* [ ] A branch está atualizada com a `main` mais recente.
* [ ] Não há código comentado, prints de debug ou arquivos desnecessários.
* [ ] Os commits seguem o padrão.

```bash
git fetch origin
git rebase origin/main     # ou: git merge origin/main
```

## Abrindo o PR

* Direcione para a `main`.
* **Título** no padrão de commit (ex: `feat: adiciona classe ContaBancaria`).
* **Vincule a issue** com `Closes #12`.
* Preencha o template (`.github/pull_request_template.md`), inclusive o campo **TDD**.
* Prefira PRs **pequenos**.

## Modelo de descrição do PR

```markdown
## Issue relacionada
Closes #

## Tipo de alteração
- [ ] Correção de bug
- [ ] Documentação
- [ ] Funcionalidade ou recurso
- [ ] Testes
- [ ] Refatoração

## O que foi feito
- Item 1
- Item 2

## TDD
- [ ] Os testes foram escritos antes do código
- [ ] Os testes foram escritos depois (justifique abaixo)

Justificativa (se os testes vieram depois):

## Como testar
Passos para o revisor validar a alteração.

## Checklist
- [ ] Critérios de aceite da issue atendidos
- [ ] Testes unitários cobrem os critérios de aceite e regras principais
- [ ] CI verde
- [ ] Funcionalidade pronta para a demo da Sprint Review
```

## Revisão de código

### Quem revisa e quantas aprovações
* **1 aprovação** é suficiente.
* Em caso de dúvida (mudança grande, delicada ou que mexe em muita coisa), peça **2 aprovações**.
* **Qualquer membro** da equipe pode revisar, desde que **não seja quem escreveu** o código.

### Prazo
* Não há prazo obrigatório, mas o ideal é revisar em até **24 horas**.
* Lembre dos PRs pendentes na daily.
* Revisar PR de colega vem antes de puxar tarefa nova.

### Responsabilidades do revisor
* Ler o código com atenção, e não aprovar só por formalidade.
* Verificar se os **critérios de aceite** foram atendidos.
* Conferir se os **testes** existem, fazem sentido e se há justificativa quando vieram depois do código.
* Se possível, baixar a branch e rodar localmente.
* Dar feedback **respeitoso, objetivo e construtivo**: critique o código, não a pessoa.

### O que checar
* [ ] Faz o que a issue pede?
* [ ] Os testes cobrem os critérios de aceite, erros e casos de borda?
* [ ] O código está legível e bem nomeado?
* [ ] Respeita encapsulamento, coesão e responsabilidade única?
* [ ] Não há duplicação ou código morto?
* [ ] O CI está verde (cobertura mínima 60%, meta de 70% no código novo)?

### Resultado
| Resultado | Significado |
| :--- | :--- |
| **Approve** | Pronto para o merge. |
| **Request changes** | Há ajustes obrigatórios antes de aprovar. |
| **Comment** | Dúvidas ou sugestões que não bloqueiam o PR. |

### Regras
* O autor responde todos os comentários e faz os ajustes na mesma branch.
* Após novos commits, o revisor reavalia o PR.
* Uma conversa só é marcada como resolvida quando o assunto foi de fato tratado.