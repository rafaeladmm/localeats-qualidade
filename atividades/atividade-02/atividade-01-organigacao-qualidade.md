# Atividade 2: Organização da Qualidade no LocalEats

## 1. Identificação

**Unidade Curricular:** Qualidade de Software  
**Metodologia:** Problem-Based Learning (PBL)  
**Projeto:** LocalEats  
**Modalidade:** Individual  
**Integrante:** Rafaela

---

# Tarefa 1: Diagnóstico da situação

| Problema identificado | Possível consequência para o produto ou para a equipe |
|---|---|
| Os critérios para considerar uma funcionalidade pronta não estão claros. | Diferentes integrantes podem ter entendimentos diferentes sobre quando uma funcionalidade está concluída, aumentando a possibilidade de funcionalidades serem disponibilizadas com problemas ou sem atender aos critérios esperados. |
| Alguns integrantes acreditam que somente o QA deve testar. | A qualidade pode ficar concentrada em um único papel, reduzindo a responsabilidade compartilhada e fazendo com que defeitos sejam identificados mais tarde no processo de desenvolvimento. |
| Defeitos são identificados, mas nem sempre são registrados ou acompanhados. | Problemas podem ser esquecidos, não ter seu andamento acompanhado ou voltar a ocorrer, dificultando a priorização e a correção dos defeitos. |

### A qualidade do LocalEats deve ser responsabilidade exclusiva do profissional de QA?

Não. A qualidade deve ser uma responsabilidade compartilhada entre os diferentes papéis envolvidos no desenvolvimento. O QA possui responsabilidades específicas relacionadas ao planejamento e execução de testes e à identificação de problemas, mas desenvolvedores, analistas, responsável pelo produto e demais envolvidos também contribuem para a qualidade. A definição de critérios, a revisão dos requisitos, a implementação e o acompanhamento dos defeitos também influenciam diretamente o resultado do produto.

---

# Tarefa 2: Papéis e competências

Como a atividade está sendo realizada individualmente, foi analisado um papel, conforme a orientação de que cada integrante seja responsável pela análise de pelo menos um papel.

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
|---|---|---|---|---|
| Rafaela | QA / Analista de Qualidade | Planejar e executar testes; verificar se as funcionalidades atendem aos critérios definidos; identificar e registrar defeitos; acompanhar os defeitos até sua resolução; comunicar os resultados dos testes; contribuir para a definição e melhoria das práticas de qualidade. | Conhecimentos de técnicas e níveis de teste; elaboração e execução de casos de teste; identificação e registro de defeitos; análise de requisitos e critérios de aceitação; uso de ferramentas de acompanhamento de defeitos e testes. | Pensamento crítico; atenção aos detalhes; comunicação clara; organização; colaboração com diferentes papéis; capacidade de questionar requisitos e resultados de forma objetiva. |

### Observação

Embora o QA tenha responsabilidades específicas de qualidade, isso não significa que ele seja o único responsável pela qualidade do produto. A organização proposta mantém a responsabilidade compartilhada entre os papéis definidos na matriz RACI.

---

# Tarefa 3: Matriz de responsabilidades — RACI

### Papéis utilizados na matriz

- **RP — Responsável pelo Produto**
- **AN — Analista de Sistemas/Negócio**
- **DEV — Desenvolvedor**
- **QA — Analista de Qualidade**

### Legenda

- **R — Responsável:** executa a atividade.
- **A — Aprovador:** responde pelo resultado final ou toma a decisão.
- **C — Consultado:** contribui antes da execução ou decisão.
- **I — Informado:** precisa conhecer o resultado.

| Atividade de qualidade | RP | AN | DEV | QA |
|---|---|---|---|---|
| Definir critérios de aceitação | A | R | C | C |
| Revisar requisitos | A | R | C | C |
| Implementar a funcionalidade | I | C | R/A | I |
| Revisar o código | I | C | R/A | C |
| Criar testes unitários | I | C | R/A | C |
| Planejar e executar testes do sistema | I | C | C | R/A |
| Registrar e acompanhar defeitos | I | C | C | R/A |
| Priorizar a correção dos defeitos | A | C | C | R |
| Aprovar a disponibilização da versão | A | C | R | C |

## Justificativa da distribuição

A distribuição procura evitar que todas as atividades de qualidade sejam concentradas no QA. O responsável pelo produto participa das decisões relacionadas aos critérios, prioridades e aprovação da versão. O analista contribui principalmente na análise e revisão dos requisitos. O desenvolvedor é responsável pela implementação e por atividades de qualidade relacionadas ao código e aos testes unitários. O QA concentra as atividades de teste do sistema e o registro e acompanhamento dos defeitos, mas participa também de outras etapas como consultado.

---

# Lacuna ou conflito encontrado

Uma possível lacuna identificada é a **definição dos critérios de aceitação**. Caso esses critérios não sejam definidos e revisados antes da implementação, o QA pode receber uma funcionalidade para testar sem possuir uma referência suficientemente clara para determinar se ela atende ao esperado.

Para evitar esse problema, o responsável pelo produto e o analista devem participar da definição e revisão dos critérios, com contribuição do desenvolvedor e do QA. Dessa forma, a equipe possui uma referência comum para desenvolvimento e testes.

---

# Práticas recomendadas de QA

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
|---|---|---|
| Definição e revisão dos critérios de aceitação antes da implementação | Ajuda a reduzir a falta de clareza sobre quando uma funcionalidade pode ser considerada pronta e diminui interpretações diferentes entre os integrantes. | RP, AN, DEV e QA |
| Registro e acompanhamento dos defeitos em uma ferramenta compartilhada | Ajuda a evitar que defeitos identificados sejam esquecidos ou deixem de ser acompanhados até sua resolução. | QA, DEV, AN e RP |

### Como essas práticas favorecem a responsabilidade compartilhada

As práticas propostas envolvem mais de um papel e fazem com que a qualidade seja considerada durante diferentes etapas do desenvolvimento. A definição dos critérios de aceitação ocorre antes dos testes e envolve diferentes participantes, enquanto o registro e acompanhamento dos defeitos permite que o problema seja conhecido e tratado pelos responsáveis pela correção e pelas decisões de prioridade.

---

# Uso de inteligência artificial

**Ferramenta utilizada:** ChatGPT.

**Como foi utilizada:** A ferramenta foi utilizada como apoio para organizar as respostas, estruturar a análise dos papéis e responsabilidades e revisar a coerência da matriz RACI.

**Como as respostas foram verificadas:** As sugestões foram comparadas com as situações, orientações, papéis e regras apresentados no enunciado da atividade. A matriz foi revisada para verificar se cada atividade possui pelo menos um responsável (R) e um único aprovador (A), conforme as regras da atividade. As decisões foram analisadas e ajustadas para manter a qualidade como responsabilidade compartilhada, evitando concentrar todas as responsabilidades no QA.
