# Desenvolvimento com TDD

Seguimos **TDD (Test-Driven Development)** como padrão: primeiro o teste, depois o código, por último a refatoração.

## Stack de testes

* Linguagem: **Python**.
* Testes: **`pytest`** (já vem com o Python, sem instalar framework).
* Cobertura: **`pytest-cov`** (usada também no [CI](ci.md)).
* Por enquanto, **só testes unitários**. Testes de integração entram quando o código estiver mais desenvolvido.
* Mocks provavelmente não serão necessários.

## O ciclo Red → Green → Refactor

1. 🔴 **Red:** escreva um teste a partir de um critério de aceite da issue. Rode e **veja ele falhar**.
2. 🟢 **Green:** escreva o **mínimo de código** para o teste passar.
3. 🔵 **Refactor:** melhore o código mantendo todos os testes passando.
4. **Repita** para o próximo critério.

## Os critérios de aceite viram testes

Cada critério de aceite da issue deve ter pelo menos um teste correspondente.

```text
Critério: "Lança exceção ao sacar mais que o saldo"
   → test_saque_maior_que_saldo_lanca_excecao
```

Exemplo em `pytest`:

```python
import pytest
from conta import ContaBancaria, SaldoInsuficienteError


def test_saque_maior_que_saldo_lanca_excecao():
    conta = ContaBancaria(saldo=100)
    with pytest.raises(SaldoInsuficienteError):
        conta.sacar(150)
```

Rodar os testes e ver a cobertura:

```bash
pytest
pytest --cov --cov-report=term-missing
```

## Quão rígido é o TDD?

O TDD não é extremamente rígido, mas tem regras:

* **Escrever o teste primeiro é o recomendado**, inclusive que o primeiro commit da branch seja o teste falhando.
* Dependendo do andamento, os testes podem ficar para o final, **desde que haja justificativa** no PR (campo "TDD" do template).
* Seja qual for a ordem, **no fim a tarefa precisa ter testes** cobrindo os critérios de aceite e as regras principais.
* O revisor confere se os testes existem e se a justificativa faz sentido.

## Regras gerais

* Um teste por comportamento, com nome descritivo.
* Teste **comportamento** (o que a classe faz), não detalhes internos.
* Cubra o caminho feliz, casos de borda e casos de erro.
* Testes independentes entre si e rápidos.
* Antes de cada commit, rode **toda** a suíte de testes.
* Para corrigir um bug: primeiro escreva um teste que reproduza o bug (ele falha), depois corrija.

## Commits acompanhando o ciclo

```text
test: adiciona teste de saque com saldo insuficiente
feat: implementa validação de saldo no saque
refactor: extrai método de validação de saldo
```