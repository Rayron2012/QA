# Gherkin

Uma boa forma de aplicar o Gherkin é quando vamos descrever  padrao de comportamento de usuario para determinada feature do projeto.

---

### Formas correttas de utilizar Gherkin

É uma linguagem criada para descrever comportamentos, e serve com documentação do projeto e também para testes automatizads, mas nao se limita somente a automatização. 

* **Mais Bobre:** Conforme estudei percebi que o Gherkin deve ser escrito voltado a regra de negócio:
  * Deve ser  escrito pensando em passo (Step) que devem explicar cada etapa de interação do usuariocom o sistema a ser testado.
  * **Gherkin:**
    * *Given **(Pt. Dado)***: Define a pré-condição ou o cenário em que você se encontra antes do teste começar. É o contexto inicial, geralmente escrito pensando no passado. Exemplo: Dado que a página de login do painel de monitoramento está aberta.
    * *When **(Pt. Quando)***: É o gatilho principal. Representa o que é executado naquele momento (no presente) para provocar uma reação do sistema. Exemplo: Quando eu insiro credenciais de administrador válidas.
    * *Then **(Pt. Então)***: É o resultado, etapa de validação, verificamos se a reação do sistema, gerada pela ação anterior, corresponde exatamente ao que era esperado. Exemplo: O dashboard principal com os alertas deve ser carregado na tela.
    * *And **(Pt. E)***: É um conector usado para adicionar mais um passo no fluxo sem precisar repetir o DADO, QUANDO, ENtÃO. Exemplo: E clico no botão "Autenticar"./
  * **Uso do And (E):** Serve como um conector para somar passos adicionais sem repetir o Dado, Quando ou Então. Ele assume o mesmo papel do passo que veio antes dele:
    - Pode adicionar mais pré-condições (Dado... E...).
    - Pode adicionar mais ações (Quando... E...).
    - Pode adicionar mais validações finais (Então... E...).

---

### Formas Incorretas de utilizar o Gherkin
