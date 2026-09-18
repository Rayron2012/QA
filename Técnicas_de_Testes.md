# Técnicas de Testes

São técnicas aplicadas de forma quase automática no trabalho e usadas de forma natural no dia a dia. É importante conhecer, saber como funcionam e como aplicá-las. Não necessariamente você precisa usar todas ao mesmo tempo, mas é muito provável que, em vários momentos da rotina, utilize grande parte delas.

---

### Partição de Equivalência

Agrupa entradas de dados em classes ou conjuntos que compartilham o mesmo comportamento esperado. Em vez de testar todas as possibilidades numéricas, classificamos por classes de equivalência. 

* **Exemplo prático:** Validar a entrada de idade em um sistema onde a regra é permitir acesso entre 18 e 60 anos:
  * Menor que 18 (`< 18`) $\rightarrow$ Exemplo de teste: 15 *(Inválido)*
  * Entre 18 e 60 (`18 a 60`) $\rightarrow$ Exemplo de teste: 25 *(Válido)*
  * Maior que 60 (`> 60`) $\rightarrow$ Exemplo de teste: 65 *(Inválido)*

Testando apenas um representante de cada grupo, cobrimos o comportamento esperado e facilitamos a execução dos testes sem redundância.

---

### Análise do Valor Limite

Normalmente utilizada para testar as fronteiras e bordas dos intervalos. Se um erro de programação for acontecer, as chances são gigantescas de ele estar exatamente na lógica de condição (como os clássicos erros de `<` em vez de `<=`).

* **Exemplo prático (usando o intervalo de 18 a 60 anos):**
  * Limite inferior (18): testamos **17** (fora/inválido) e **18** (fronteira/válido).
  * Limite superior (60): testamos **60** (fronteira/válido) e **61** (fora/inválido).

Idealmente, focamos nos valores mínimos, máximos e nos números imediatamente adjacentes a eles.

---

### Tabela de Decisão

Técnica focada em regras de negócio complexas onde diversas condições combinadas geram ações diferentes. 

* **Exemplo prático:** Ganhar frete grátis em compras acima de R$ 200,00. A ideia aqui é mapear se uma ou mais condições ativam o benefício (e se o desconto não é aplicado caso o carrinho contenha itens restritos, como bebidas alcoólicas, por exemplo).
* Independentemente de qual seja a regra aplicada, cruzamos as combinações para validar se o comportamento do sistema entra em prática conforme as condições previamente estabelecidas.

---

### Transição de Estados

Utilizada para avaliar como o sistema se comporta após várias interações em sequência feitas pelo usuário. 

* **Exemplo prático:** O ciclo de vida de um pedido de delivery:  
  `Criado` $\rightarrow$ `Pago` $\rightarrow$ `Enviado` $\rightarrow$ `Entregue`
* O objetivo é validar se o fluxo avança conforme o planejado e impedir/detectar caminhos inválidos (como um pedido `Criado` saltar diretamente para `Entregue`).

---

### Teste Baseado em Erro / Suposição (Error Guessing)

Uma técnica fortemente baseada na experiência e na intuição. Conforme você adquire vivência de mercado e conhece os hábitos do time ou as falhas típicas do ciclo de desenvolvimento, passa a prever melhor onde o sistema tende a quebrar.

* **Exemplo prático:** Inserir emojis em campos de texto/senha, colar textos longos em formulários curtos ou submeter caracteres especiais e sequências numéricas inesperadas para ver se a aplicação trata o erro corretamente.

---

### Teste Exploratório

É a abordagem mais dinâmica, interativa e flexível do dia a dia. Nela, o testador explora ativamente a aplicação sem roteiros predefinidos, caçando possíveis falhas com base na sua experiência, intuição e observação imediata da tela. É uma técnica valiosa principalmente quando o tempo é curto, a documentação é escassa ou os requisitos mudam com facilidade. Não elimina a necessidade de testes estruturados, funcionando como um complemento essencial.

---

### Teste Baseado em Caso de Uso

Diferente do teste exploratório, essa técnica é altamente estruturada e orientada a objetivos claros, acompanhando a jornada do usuário de ponta a ponta. Foca em como o ator interage com o sistema para atingir uma meta, validando tanto o fluxo principal (caminho feliz) quanto os fluxos alternativos e exceções com base nas especificações do negócio.

---

### Teste De Mutação 

O Teste de Mutação é uma abordagem avançada de teste de software focada em avaliar a qualidade e a eficácia dos próprios casos de teste, cria mutantes no códigos da aplicação, para validar a força da suite de testes, se os testes não falham com essas alterações é sinal de que a suite esta fragil.

Em resumo, é uma técnica usada não para testar o software diretamente, mas para testar se os seus testes realmente conseguem encontrar problemas no código.
