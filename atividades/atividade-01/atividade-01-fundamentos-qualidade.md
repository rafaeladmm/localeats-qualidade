# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

## 1. Identificação

**Unidade Curricular:** Qualidade de Software  
**Metodologia:** Problem-Based Learning (PBL)  
**Projeto:** LocalEats  
**Modalidade:** Individual  
**Integrante:** Rafaela

---

# Tarefa 1: Fundamentos da qualidade

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
|---|---|---|---|
| Explícita | O usuário deve conseguir realizar pedidos no LocalEats. | Usuário/cliente | O usuário não consegue utilizar a funcionalidade de pedido, impedindo a realização da compra pelo sistema. |
| Explícita | O usuário deve conseguir consultar os pedidos realizados. | Usuário/cliente | O usuário não consegue verificar os pedidos que já realizou. |
| Implícita | O valor total do pedido deve ser apresentado de forma consistente com os preços exibidos e as quantidades selecionadas. | Usuário/cliente e restaurante | O usuário pode visualizar um valor diferente do esperado, gerando dúvidas sobre o valor do pedido e reduzindo a confiança no sistema. |
| Implícita | As informações apresentadas durante a realização do pedido devem ser consistentes e compreensíveis. | Usuário/cliente | O usuário pode ter dificuldade para verificar se o pedido e seus valores estão corretos antes de finalizá-lo. |

### Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade?

Sim. A implementação das funcionalidades solicitadas não garante, por si só, que o sistema atenda às necessidades implícitas dos usuários.

Por exemplo, o LocalEats pode permitir que o usuário realize pedidos, mas apresentar um total diferente do esperado a partir dos preços exibidos e das quantidades selecionadas.

Nesse caso, a funcionalidade existe, porém há uma inconsistência no resultado apresentado ao usuário, o que pode comprometer a confiança no sistema.

---

# Tarefa 2: Exploração da aplicação

## Funcionalidade escolhida

**Fazer pedido.**

## Teste realizado

Foi selecionado o **Prato Especial 1**, cujo preço exibido na interface é **R$ 17,91**, e o **Prato Especial 3**, cujo preço exibido é **R$ 69,23**.

Foram testadas quantidades de 1 a 7 unidades. Em cada caso, o total esperado foi calculado com base no valor utilizado como referência no teste e comparado com o total apresentado pelo sistema.

Durante a exploração, foi observado que, a partir de determinadas quantidades, o sistema apresenta um valor superior ao cálculo esperado.

### Prato Especial 1 — R$ 17,91

| Quantidade | Total calculado | Total apresentado pelo sistema | Diferença |
|---:|---:|---:|---:|
| 1 | R$ 17,91 | R$ 17,91 | R$ 0,00 |
| 2 | R$ 35,81 | R$ 35,82 | + R$ 0,01 |
| 3 | R$ 53,72 | R$ 53,73 | + R$ 0,01 |
| 4 | R$ 71,62 | R$ 71,64 | + R$ 0,02 |
| 5 | R$ 89,53 | R$ 89,55 | + R$ 0,02 |
| 6 | R$ 107,44 | R$ 107,46 | + R$ 0,02 |
| 7 | R$ 125,34 | R$ 125,37 | + R$ 0,03 |

### Prato Especial 3 — R$ 69,23

| Quantidade | Total calculado | Total apresentado pelo sistema | Diferença |
|---:|---:|---:|---:|
| 1 | R$ 69,23 | R$ 69,23 | R$ 0,00 |
| 2 | R$ 138,45 | R$ 138,46 | + R$ 0,01 |
| 3 | R$ 207,68 | R$ 207,69 | + R$ 0,01 |
| 4 | R$ 276,90 | R$ 276,92 | + R$ 0,02 |
| 5 | R$ 346,13 | R$ 346,15 | + R$ 0,02 |
| 6 | R$ 415,36 | R$ 415,38 | + R$ 0,02 |
| 7 | R$ 484,58 | R$ 484,61 | + R$ 0,03 |

## Registro da exploração

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
|---|---|---|---|---|
| Rafaela | Fazer pedido | Foram selecionados dois produtos, com preços exibidos de R$ 17,91 e R$ 69,23. Foram testadas quantidades de 1 a 7 unidades e os totais apresentados pelo sistema foram comparados com os cálculos realizados durante os testes. | Com 1 unidade, o total apresentado correspondeu ao valor de referência. A partir de 2 unidades, foram observadas diferenças de alguns centavos. Nos dois produtos testados, o sistema apresentou valores superiores aos cálculos realizados, chegando a uma diferença de R$ 0,03 com 7 unidades. | Capturas de tela dos testes, armazenadas na pasta `evidencias/`. |

### Utilização esperada

Selecionar um produto, adicionar uma quantidade válida ao pedido e verificar se o total apresentado corresponde ao valor esperado para o preço e a quantidade selecionada.

### Utilização alternativa

Aumentar progressivamente a quantidade de um mesmo produto e comparar o total apresentado pelo sistema com o cálculo realizado durante o teste.

Essa abordagem permite verificar se o comportamento do total permanece consistente conforme a quantidade do produto é alterada.

### Observação sobre o resultado

O teste demonstra um comportamento observável na interface: o total apresentado pelo sistema pode ser diferente do resultado obtido no cálculo realizado durante o teste.

Nos dois produtos analisados, a partir de 2 unidades foram observadas diferenças positivas entre o valor calculado e o valor apresentado pelo sistema. A diferença chegou a **R$ 0,03 com 7 unidades**.

O teste não permite determinar a causa dessa diferença. Portanto, não foi considerado como fato que exista um erro de ponto flutuante, arredondamento interno ou utilização de outro valor no banco de dados.

Para determinar a causa seria necessário analisar a implementação interna da aplicação e/ou os dados utilizados pelo sistema.

---

# Tarefa 3: Requisitos e características de qualidade

| Integrante | Requisito de qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |
|---|---|---|---|---|
| Rafaela | O sistema deve calcular e apresentar o total do pedido de forma consistente com os preços unitários exibidos e as quantidades selecionadas para os produtos. | Adequação funcional — correção funcional | O requisito está diretamente relacionado à funcionalidade de fazer pedido. O usuário precisa receber um total coerente com as informações apresentadas na interface. Nos testes realizados, foram observadas diferenças entre o cálculo realizado e o total apresentado pelo sistema. | Selecionar diferentes produtos, registrar os preços exibidos e testar diferentes quantidades. Calcular o total esperado e comparar com o total apresentado pelo sistema, registrando eventuais diferenças. |

## Justificativa da característica escolhida

A característica predominante é **adequação funcional**, com foco na **correção funcional**, porque a análise está relacionada ao resultado produzido pela funcionalidade de realização do pedido.

O sistema possui a funcionalidade de fazer pedido, mas o teste verificou se o resultado do cálculo apresentado ao usuário é consistente com os dados e quantidades utilizados no pedido.

---

# Uso de inteligência artificial

**Ferramenta utilizada:** ChatGPT.

**Como foi utilizada:** A ferramenta foi utilizada como apoio para organizar as respostas, conferir os cálculos realizados durante os testes e estruturar a análise da qualidade do LocalEats.

**Como as respostas foram verificadas:** As respostas foram conferidas com base nas instruções da atividade e nos resultados observados diretamente na aplicação. Os cálculos dos totais foram realizados e conferidos manualmente durante a análise.

As possíveis causas internas para as diferenças não foram tratadas como fatos, pois não houve acesso ao código-fonte ou ao banco de dados da aplicação.

---

# Evidências

As capturas de tela utilizadas na análise estão armazenadas em:

`atividades/atividade-01/evidencias/`
