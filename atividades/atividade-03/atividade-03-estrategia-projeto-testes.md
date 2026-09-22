# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## 1. Identificação

**Unidade Curricular:** Qualidade de Software  
**Metodologia:** Problem-Based Learning (PBL)  
**Projeto:** LocalEats  
**Modalidade:** Individual  
**Integrante:** Rafaela

---

# Tarefa 1: Planejamento dos testes

## 1.1 Objetivo dos testes

Verificar se a funcionalidade de **fazer pedido** apresenta resultados consistentes para diferentes formas de composição do pedido, principalmente em relação ao cálculo e à apresentação do valor total. O planejamento busca priorizar situações com potencial de gerar divergências no valor apresentado ao usuário e definir casos de teste representativos para essas situações.

## 1.2 Escopo

| Integrante | Funcionalidade incluída | O que será verificado |
|---|---|---|
| Rafaela | Fazer pedido | Inclusão de produtos no pedido, alteração da quantidade e consistência do total apresentado em diferentes composições de pedido. |

### Funcionalidade não incluída

| Funcionalidade não incluída | Justificativa |
|---|---|
| Consultar pedidos | Não faz parte do fluxo de fazer e validar o cálculo do pedido selecionado para esta atividade. |

## 1.3 Abordagem

| Item | Decisão da equipe | Justificativa |
|---|---|---|
| Níveis de teste | Sistema | A funcionalidade será analisada pelo fluxo completo disponível na interface do LocalEats, verificando as entradas fornecidas pelo usuário e os resultados apresentados pelo sistema. |
| Tipos de teste | Funcional | O foco está em verificar o comportamento esperado da funcionalidade de fazer pedido e do cálculo apresentado ao usuário. |
| Perspectiva caixa-preta ou caixa-branca | Caixa-preta | Os testes serão projetados a partir das entradas e dos resultados observáveis na interface, sem considerar a implementação interna do sistema. |
| Técnica de teste | Particionamento de equivalência | A técnica permite organizar diferentes formas de composição do pedido em classes representativas, evitando a necessidade de testar todas as combinações possíveis. |

## 1.4 Ambiente e responsabilidades

| Item | Definição |
|---|---|
| Ambiente necessário | Aplicação LocalEats disponível em `https://local-eats-unisenac.vercel.app/`, navegador web, dispositivo com acesso à internet e acesso às funcionalidades necessárias para realizar um pedido. |
| Responsáveis pelo planejamento | Rafaela |
| Responsáveis pela especificação dos casos | Rafaela |
| Responsáveis pela futura execução | Rafaela |

## 1.5 Critérios

| Critério | Definição da equipe |
|---|---|
| Entrada | Aplicação disponível, acesso ao fluxo de fazer pedido e produtos disponíveis para seleção. |
| Saída | Os três casos de teste planejados estão especificados, revisados e rastreáveis aos riscos e à técnica escolhida. A execução e o registro dos resultados ocorrerão posteriormente. |
| Suspensão | Aplicação indisponível, impossibilidade de acessar o fluxo de pedido ou ausência de produtos necessários para a execução dos casos. |

---

# Tarefa 2: Riscos e técnicas de teste

## 2.1 Análise dos riscos

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
|---|---|---|---|---|---|---|---|---|
| R01 | Rafaela | Fazer pedido | O total apresentado no pedido pode não corresponder ao resultado esperado a partir dos valores e quantidades dos itens selecionados. | O usuário pode visualizar um valor incorreto ou inconsistente em relação aos itens do pedido, comprometendo a confiança na informação apresentada. | Média | Alta | Alta | O cálculo do total é uma informação diretamente relacionada ao pedido. Uma divergência pode afetar o valor que o usuário espera pagar e, por isso, possui impacto alto. |
| R02 | Rafaela | Fazer pedido | A alteração da quantidade de um produto pode não atualizar o total do pedido de forma consistente. | O pedido pode apresentar um total incompatível com a quantidade selecionada, fazendo com que o usuário visualize uma informação incorreta antes de concluir o pedido. | Média | Alta | Alta | A quantidade é uma entrada diretamente relacionada ao total. Uma falha na atualização pode alterar o resultado apresentado ao usuário e comprometer a confiabilidade do pedido. |

## 2.2 Aplicação da técnica

### Integrante responsável

**Nome:** Rafaela  
**Funcionalidade:** Fazer pedido  
**Riscos relacionados:** R01 e R02  
**Técnica escolhida:** Tabela de decisão

### Por que a técnica foi escolhida?

A tabela de decisão é adequada porque o resultado esperado do total depende da combinação de condições do pedido, como a quantidade de produtos e a quantidade selecionada para cada item. A técnica permite representar diferentes combinações de condições e relacioná-las aos comportamentos esperados, mantendo os casos de teste vinculados aos riscos identificados.

### Aplicação da técnica

Foram consideradas duas condições observáveis no fluxo de pedido:

- **Quantidade de produtos no pedido:** um produto ou dois ou mais produtos.
- **Quantidade de cada produto:** uma unidade ou mais de uma unidade.

| Regra | Quantidade de produtos | Quantidade | Resultado esperado |
|---|---|---|---|
| R1 | 1 produto | 1 unidade | Total corresponde ao valor do produto selecionado. |
| R2 | 1 produto | Mais de 1 unidade | Total é atualizado conforme a quantidade selecionada e permanece consistente com o valor unitário apresentado. |
| R3 | 2 ou mais produtos | 1 unidade de cada | Total corresponde à soma dos valores dos produtos selecionados. |
| R4 | 2 ou mais produtos | Pelo menos um produto com mais de 1 unidade | Total corresponde à soma dos valores considerando as respectivas quantidades. |

### Casos derivados

- **CT01:** Verificar o total de um pedido com um produto e uma unidade — relacionado à regra R1.
- **CT02:** Verificar o total após aumentar a quantidade de um produto — relacionado à regra R2.
- **CT03:** Verificar o total de um pedido com produtos diferentes — relacionado às regras R3/R4.

# Tarefa 3: Casos de teste e rastreabilidade

## 3.1 Especificação dos casos de teste

### CT01: Calcular o total de um pedido com uma unidade

**Integrante responsável:** Rafaela  
**Funcionalidade:** Fazer pedido  
**Risco ou requisito relacionado:** R01 — consistência do total do pedido  
**Técnica utilizada:** Tabela de decisão

**Pré-condição:**
- A aplicação está disponível.
- Existe pelo menos um produto disponível para seleção.
- O usuário consegue acessar o fluxo de fazer pedido.

**Dados de entrada:**
- Um produto disponível.
- Quantidade: 1 unidade.

**Passos:**
1. Acessar a funcionalidade de fazer pedido.
2. Selecionar um produto disponível.
3. Adicionar uma unidade do produto ao pedido.
4. Consultar o total apresentado pelo sistema.

**Resultado esperado:**
O total apresentado deve corresponder ao valor do produto selecionado para a quantidade de uma unidade.

---

### CT02: Calcular o total de várias unidades do mesmo produto

**Integrante responsável:** Rafaela  
**Funcionalidade:** Fazer pedido  
**Risco ou requisito relacionado:** R01 e R02 — consistência do total e atualização conforme a quantidade  
**Técnica utilizada:** Tabela de decisão

**Pré-condição:**
- A aplicação está disponível.
- Existe pelo menos um produto disponível para seleção.
- O usuário consegue acessar o fluxo de fazer pedido.

**Dados de entrada:**
- Um produto disponível.
- Quantidade: 2 ou mais unidades.

**Passos:**
1. Acessar a funcionalidade de fazer pedido.
2. Selecionar um produto disponível.
3. Alterar a quantidade do produto para mais de uma unidade.
4. Consultar o total apresentado pelo sistema.
5. Comparar o total apresentado com o cálculo obtido a partir do valor unitário exibido e da quantidade selecionada.

**Resultado esperado:**
O total apresentado deve ser atualizado de acordo com a quantidade selecionada e ser consistente com o valor unitário apresentado para o produto.

---

### CT03: Calcular o total de um pedido com produtos diferentes

**Integrante responsável:** Rafaela  
**Funcionalidade:** Fazer pedido  
**Risco ou requisito relacionado:** R01 — consistência do total do pedido  
**Técnica utilizada:** Tabela de decisão

**Pré-condição:**
- A aplicação está disponível.
- Existem pelo menos dois produtos diferentes disponíveis.
- O usuário consegue acessar o fluxo de fazer pedido.

**Dados de entrada:**
- Dois ou mais produtos diferentes.
- Quantidades válidas para os produtos selecionados.

**Passos:**
1. Acessar a funcionalidade de fazer pedido.
2. Selecionar o primeiro produto e adicioná-lo ao pedido.
3. Selecionar um segundo produto diferente e adicioná-lo ao mesmo pedido.
4. Verificar os valores apresentados para os itens.
5. Consultar o total final do pedido.
6. Comparar o total apresentado com a soma dos valores esperados para os itens selecionados.

**Resultado esperado:**
O total apresentado deve corresponder à soma dos valores dos produtos e quantidades selecionados no pedido.

> **Observação:** os casos acima são casos planejados e não foram executados nesta atividade, conforme orientação do enunciado. Portanto, não foi incluído resultado obtido, apenas o resultado esperado.

---

## 3.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
|---|---|---|---|---|
| Rafaela | Fazer pedido | R01: o total apresentado pode não corresponder aos valores e quantidades dos itens selecionados | Tabela de decisão | CT01, CT02 e CT03 |
| Rafaela | Fazer pedido | R02: alteração da quantidade pode não atualizar o total de forma consistente | Tabela de decisão | CT02 |

### Verificação da rastreabilidade

A matriz permite identificar a relação entre a funcionalidade analisada, os riscos, a técnica selecionada e os casos de teste planejados. O risco R01 possui três casos relacionados e o risco R02 possui o CT02 como caso diretamente relacionado.

---

# Uso de inteligência artificial

**Ferramenta utilizada:** ChatGPT.

**Como foi utilizada:** A ferramenta foi utilizada como apoio para interpretar o enunciado, estruturar o plano de testes, sugerir riscos relacionados à funcionalidade de fazer pedido, comparar técnicas de teste e revisar a clareza dos casos de teste e da matriz de rastreabilidade.

**Uma sugestão que precisou ser alterada ou rejeitada:** A primeira proposta utilizava particionamento de equivalência para separar formas de composição do pedido. Após revisar a aplicação formal da técnica, essa abordagem foi substituída por uma tabela de decisão, pois o risco identificado envolve combinações entre quantidade de produtos e quantidade de unidades.

**Como as respostas foram verificadas:** As decisões foram comparadas diretamente com as orientações da Atividade 3, especialmente quanto à necessidade de selecionar uma funcionalidade, analisar dois riscos, aplicar pelo menos uma técnica, elaborar três casos de teste e manter a rastreabilidade entre funcionalidade, risco, técnica e casos. Os casos foram revisados para conter pré-condições, dados de entrada, passos e resultados esperados observáveis, sem incluir resultados de execução.
