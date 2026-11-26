# Boas Práticas de POO e Código

## Princípios de POO

* **Encapsulamento:** atributos privados; exponha apenas o necessário por métodos.
* **Abstração:** modele apenas o que importa para o domínio do problema.
* **Herança:** use só quando existir relação "é um". Prefira **composição** quando fizer sentido.
* **Polimorfismo:** programe para interfaces/abstrações, não para implementações concretas.

## SOLID

* **S** (Responsabilidade Única): cada classe tem um único motivo para mudar.
* **O** (Aberto/Fechado): aberta para extensão, fechada para modificação.
* **L** (Substituição de Liskov): subclasses substituem suas superclasses sem quebrar o comportamento.
* **I** (Segregação de Interfaces): várias interfaces pequenas são melhores que uma grande.
* **D** (Inversão de Dependência): dependa de abstrações, não de classes concretas.

## Código limpo

* Nomes que revelem a intenção (classes são substantivos, métodos são verbos).
* Métodos pequenos que fazem uma coisa só.
* Evite números e textos "mágicos": use constantes.
* Evite duplicação (DRY), sem abstrair cedo demais.
* Trate erros com exceções adequadas e mensagens claras.
* Comente o **porquê**, não o **o quê**.
* Mantenha um padrão único de formatação no projeto.

## Python

* Siga a **PEP 8** (nomes em `snake_case` para funções e variáveis, `PascalCase` para classes).
* Use **type hints** nos parâmetros e retornos para deixar o código mais claro.
* Use `@property` para controlar acesso a atributos, em vez de métodos `get`/`set`.
* Atributos "privados" usam `_` ou `__` como prefixo (convenção do Python).
* Use `abc.ABC` e `@abstractmethod` para classes e métodos abstratos.

## Trabalho em equipe

* Avise quando começar, travar ou terminar uma tarefa.
* Revise PRs dos colegas com agilidade; não deixe PR parado por dias.
* Divida o trabalho para duas pessoas não mexerem nos mesmos arquivos ao mesmo tempo.
* Nunca versione arquivos de IDE, builds ou dados sensíveis (use `.gitignore`).