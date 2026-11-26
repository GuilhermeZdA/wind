# Integração Contínua (CI)

A cada push e a cada Pull Request, o CI roda automaticamente (GitHub Actions).

## O que o CI verifica

* **Todos os testes unitários** (`pytest`).
* **Cobertura mínima de 60%** no projeto (`pytest-cov`). Se ficar abaixo, o CI falha.
* A **meta é 70%** de cobertura no código novo. Ela é conferida na revisão do PR.

## Regras

* **PR com CI vermelho não pode ser mergeado.**
* Se o CI falhar, quem abriu o PR é responsável por corrigir.
* Nunca desative, ignore ou "pule" testes para fazer o CI passar.
* Se passa local mas falha no GitHub, investigue diferenças de ambiente (versão do Python, dependências).
* Se o CI quebrar na `main`, veja [merge.md](merge.md#quando-o-ci-quebra-na-main).
