Repo criado para entrega do desafio "Treinando uma IA de aprendizagem: Explore o Poder do NotebookLM " do Bootcamp Santander - Automação com N8N

# Caderno Temático — Previsão de Séries Temporais

> **Caderno temático desenvolvido a partir do estudo de previsão de séries temporais, com foco na consolidação de conceitos, métodos e práticas aplicáveis ao Trabalho de Conclusão de Curso (TCC).**

## 📌 Contexto e objetivos

O assunto escolhido para este caderno temático foi **previsão de séries temporais**, tema diretamente relacionado ao meu TCC, no qual estudo a aplicação e a comparação de modelos preditivos para métricas de marketing digital.

A escolha do tema surgiu da necessidade de compreender, de forma estruturada, os fundamentos estatísticos e as principais técnicas utilizadas para analisar dados ordenados no tempo e produzir previsões úteis para apoiar a tomada de decisão.

### Objetivos de estudo

- Compreender os fundamentos de séries temporais e previsão;
- Identificar padrões como **tendência, sazonalidade, ciclos e ruído**;
- Aprender a explorar e visualizar séries temporais adequadamente;
- Entender técnicas de decomposição e transformação dos dados;
- Estudar modelos clássicos de previsão, especialmente **suavização exponencial e ARIMA**;
- Conhecer modelos de regressão aplicados a séries temporais;
- Compreender o uso de variáveis explicativas e regressão dinâmica;
- Conhecer abordagens mais avançadas, incluindo métodos hierárquicos;
- Desenvolver critérios para avaliar e comparar previsões;
- Utilizar IA generativa como ferramenta de apoio ao estudo, mantendo a validação crítica das informações e das fontes;
- Construir uma base conceitual que possa ser aplicada posteriormente ao desenvolvimento e à avaliação dos modelos do TCC.

---

## 🧭 Mapa de estudos

A organização do caderno foi estruturada a partir dos principais capítulos e conceitos identificados no material **Previsão: Princípios e prática (3ª ed.)**, complementados por outras fontes.

```text
Previsão: Princípios e prática
│
├── 1. Introdução
│   ├── O que pode ser previsto?
│   ├── Metas e planejamento
│   ├── Dados e métodos de previsão
│   ├── Etapas básicas da tarefa
│   └── Perspectiva estatística
│
├── 2. Gráficos para séries temporais
│   ├── Objetos do tipo tsibble
│   ├── Padrões em séries temporais
│   ├── Sazonalidade e sub-séries
│   ├── Autocorrelação e lags
│   └── Ruído branco
│
├── 3. Decomposição
│   ├── Transformações e ajustes
│   ├── Componentes cronológicas
│   ├── Médias móveis
│   └── Decomposição STL
│
├── 4. Features em séries temporais
├── 5. O toolbox para previsão
├── 6. Previsões de julgamento
├── 7. Modelos de regressão
├── 8. Suavização exponencial
├── 9. Modelos ARIMA
├── 10. Regressão dinâmica
├── 11. Séries hierárquicas
├── 12. Métodos avançados
├── 13. Questões práticas
└── Software e recursos
```

O mapa mental completo utilizado como referência pode ser mantido no repositório, por exemplo em `docs/mapa-mental.png`.

---

# 📚 Curadoria de fontes

As fontes foram selecionadas para combinar **fundamentação conceitual, aplicação prática e exemplos de séries temporais**. Os materiais foram utilizados como base para consultas no NotebookLM.

## Fontes principais

### 1. Artigo disponível no PubMed Central

[PMC — artigo sobre séries temporais/previsão](https://pmc.ncbi.nlm.nih.gov/articles/PMC12751667/)

**Uso no estudo:** fonte acadêmica complementar para ampliar a compreensão sobre previsão e aplicação de métodos em séries temporais.

### 2. Artigo da Sociedade Brasileira de Computação

[SBC — artigo disponível na Biblioteca Digital da SBC](https://sol.sbc.org.br/index.php/bresci/article/view/36917/36703)

**Uso no estudo:** material complementar em português, utilizado especialmente por apresentar uma abordagem mais acessível e fácil de acompanhar durante a etapa inicial de estudo.

### 3. Previsão: Princípios e prática — 3ª edição

[Forecasting: Principles and Practice — Hyndman & Athanasopoulos](https://otexts.com/fpp3/)

**Uso no estudo:** principal referência conceitual do caderno. O material aborda desde a introdução à previsão até gráficos, decomposição, features, regressão, suavização exponencial, ARIMA, regressão dinâmica, séries hierárquicas e métodos avançados.

### 4. Análise de Séries Temporais

[Análise de Séries Temporais — Biblioteca Virtual](https://plataforma.bvirtual.com.br/Leitor/Publicacao/164072/pdf/0?code=zp62NEvNG481nSQtS56sjS9mfAsGtKvhT2lZIT3cdwAcCwhGhx2PCvgnKT2W5v4SLvMBNej/d+CBbuGh48pujw==)

**Uso no estudo:** material complementar para aprofundar os conceitos de componentes de uma série temporal, especialmente **tendência, sazonalidade, ciclo e ruído**.

> **Observação:** o acesso à Biblioteca Virtual pode depender das permissões da instituição/conta utilizada. Por isso, esta fonte é tratada como complementar quando a exigência for exclusivamente por materiais de acesso aberto.

## 🎥 Material audiovisual complementar

[Vídeo sobre séries temporais e previsão](https://www.youtube.com/watch?v=fxx_E0ojKrc)

**Uso no estudo:** reforço visual e didático dos conceitos estudados nas fontes textuais.

---

# 🧠 Resumo estruturado do assunto

## 1. Introdução à previsão

Previsão de séries temporais consiste em utilizar informações observadas ao longo do tempo para estimar valores futuros. A tarefa não se limita à escolha de um algoritmo: envolve definir o objetivo, compreender os dados, selecionar uma estratégia de modelagem, gerar previsões e avaliar o desempenho.

Uma boa tarefa de previsão começa pela definição clara de **o que será previsto, em qual horizonte e para qual finalidade**.

### Ideias-chave

- A previsão deve estar ligada a uma necessidade prática;
- O horizonte de previsão influencia a escolha do método;
- O histórico da série contém informações relevantes sobre seu comportamento;
- A avaliação deve respeitar a ordem temporal dos dados;
- Métodos simples são importantes como referências de comparação.

---

## 2. Gráficos para séries temporais

A visualização é uma das primeiras etapas da análise. Um gráfico temporal pode revelar padrões que não seriam percebidos apenas por estatísticas descritivas.

### Principais elementos

- **Tendência:** movimento sistemático de longo prazo;
- **Sazonalidade:** comportamento que se repete em períodos conhecidos;
- **Ciclo:** oscilações de duração variável, normalmente associadas a condições mais amplas do fenômeno;
- **Ruído:** variações não explicadas pelo padrão sistemático da série;
- **Lag:** distância entre observações utilizadas para analisar dependência temporal;
- **Autocorrelação:** relação entre observações da série e seus valores defasados.

A identificação desses padrões ajuda a decidir quais transformações, variáveis e modelos podem ser apropriados.

---

## 3. Decomposição de séries temporais

A decomposição busca separar uma série em componentes interpretáveis. Uma visão clássica considera elementos como tendência, sazonalidade e componente irregular.

Entre as ferramentas estudadas está a **decomposição STL (Seasonal-Trend decomposition using LOESS)**, que permite separar tendência e sazonalidade de forma flexível.

### Conceitos associados

- Transformações;
- Ajustes da série;
- Médias móveis;
- Componentes cronológicas;
- Decomposição STL.

---

## 4. Features em séries temporais

Features são características extraídas da série que ajudam a descrever seu comportamento. Podem ser utilizadas para análise exploratória, diagnóstico e modelagem.

Exemplos incluem características relacionadas a tendência, sazonalidade, autocorrelação, distribuição e comportamento recente da série.

---

## 5. Toolbox para previsão

Não existe um único método universalmente superior. A escolha deve considerar o comportamento dos dados, o objetivo, o horizonte de previsão, a disponibilidade de variáveis explicativas e o desempenho observado em dados fora da amostra.

Um princípio importante é estabelecer **modelos de referência (benchmarks)** antes de interpretar modelos mais complexos.

---

## 6. Previsões de julgamento

Nem toda previsão depende exclusivamente de modelos estatísticos. Em determinadas situações, informações externas e conhecimento especializado podem complementar os dados históricos.

O conhecimento de especialistas pode ser útil, mas deve ser utilizado de forma transparente e, quando possível, avaliado em conjunto com métodos quantitativos.

---

## 7. Modelos de regressão

Modelos de regressão permitem relacionar uma variável de interesse a uma ou mais variáveis explicativas.

Em séries temporais, entretanto, é necessário considerar que as observações possuem dependência temporal. Por isso, a regressão pode ser combinada com características temporais, defasagens e outras informações relevantes.

---

## 8. Suavização exponencial

Métodos de suavização exponencial produzem previsões atribuindo diferentes pesos às observações passadas, geralmente dando maior importância às observações recentes.

A família inclui métodos capazes de representar diferentes combinações de:

- nível;
- tendência;
- sazonalidade.

---

## 9. Modelos ARIMA

ARIMA é uma família de modelos estatísticos voltados para séries temporais, baseada na combinação de componentes autorregressivos, diferenciação e médias móveis.

A estrutura geral é representada por **ARIMA(p,d,q)**:

- `p`: ordem autorregressiva;
- `d`: grau de diferenciação;
- `q`: ordem da média móvel.

Quando existe sazonalidade, podem ser considerados modelos sazonais, formando estruturas como **SARIMA**. Quando variáveis explicativas são incorporadas, surgem extensões como **ARIMAX/SARIMAX**, dependendo da estrutura adotada.

---

## 10. Regressão dinâmica

A regressão dinâmica combina uma estrutura de regressão com componentes que representam a dependência temporal dos erros ou da própria série.

Esse tipo de abordagem é particularmente relevante quando o comportamento futuro pode depender tanto do histórico da variável-alvo quanto de variáveis explicativas.

---

## 11. Séries hierárquicas

Séries hierárquicas aparecem quando os dados possuem diferentes níveis de agregação. Um exemplo seria possuir valores por produto, região e total geral.

O desafio é produzir previsões que possam ser utilizadas nos diferentes níveis da hierarquia de maneira coerente.

---

## 12. Métodos avançados

Depois dos métodos clássicos, existem abordagens mais sofisticadas que podem incorporar diferentes estruturas, modelos e estratégias de combinação.

O princípio central continua sendo o mesmo: **a complexidade do modelo deve ser justificada pelo problema e pelo desempenho obtido em avaliação adequada**.

---

## 13. Questões práticas

Uma previsão aplicada precisa considerar mais do que a execução de um algoritmo.

Aspectos importantes incluem:

- qualidade dos dados;
- valores ausentes e zeros;
- outliers;
- mudanças estruturais;
- definição do horizonte;
- divisão temporal entre treino, validação e teste;
- prevenção de vazamento de dados;
- escolha das métricas;
- interpretação dos resíduos;
- comunicação dos resultados.

---

# 📖 Glossário

| Conceito | Definição resumida |
|---|---|
| **Série temporal** | Conjunto de observações organizadas em ordem cronológica. |
| **Previsão** | Estimativa de valores futuros a partir das informações disponíveis. |
| **Tendência** | Movimento sistemático de longo prazo da série. |
| **Sazonalidade** | Padrão que se repete em intervalos regulares. |
| **Ciclo** | Oscilação de duração não necessariamente fixa, diferente da sazonalidade regular. |
| **Ruído** | Variação irregular não explicada pelos principais padrões da série. |
| **Lag** | Defasagem temporal entre observações. |
| **Autocorrelação** | Medida da relação entre uma série e seus valores defasados. |
| **Ruído branco** | Processo sem autocorrelação relevante, com média constante e variância constante sob as condições usuais. |
| **Decomposição** | Separação da série em componentes como tendência, sazonalidade e erro. |
| **STL** | Método de decomposição de série temporal baseado em LOESS. |
| **Feature** | Característica extraída dos dados para representar algum aspecto da série. |
| **Benchmark** | Modelo de referência utilizado para contextualizar o desempenho de outros modelos. |
| **Suavização exponencial** | Família de métodos que atribui pesos decrescentes às observações passadas. |
| **AR** | Componente autorregressivo que utiliza valores passados da série. |
| **MA** | Componente de média móvel baseado em erros passados. |
| **ARIMA** | Modelo que combina autorregressão, diferenciação e média móvel. |
| **SARIMA** | Extensão do ARIMA que incorpora estrutura sazonal. |
| **ARIMAX** | Estrutura ARIMA que incorpora variáveis explicativas externas. |
| **SARIMAX** | Modelo que combina componentes ARIMA, sazonalidade e variáveis exógenas. |
| **Regressão dinâmica** | Regressão que considera relações temporais e dependência serial. |
| **Walk-forward validation** | Estratégia de avaliação que avança no tempo, treinando com o passado e prevendo períodos posteriores. |
| **Horizonte de previsão** | Quantidade de períodos futuros que serão previstos. |
| **Resíduo** | Diferença entre o valor observado e o valor ajustado/previsto pelo modelo. |
| **MAE** | Erro absoluto médio. |
| **RMSE** | Raiz do erro quadrático médio. |
| **MAPE** | Erro percentual absoluto médio. |
| **sMAPE** | Versão simétrica do erro percentual absoluto médio. |
| **MASE** | Erro absoluto escalado pela performance de um modelo de referência. |
| **Ljung-Box** | Teste utilizado para verificar autocorrelação residual em conjunto de defasagens. |
| **ACF** | Função de autocorrelação. |
| **Validação temporal** | Avaliação que preserva a ordem cronológica dos dados. |
| **Vazamento de dados** | Uso indevido de informações futuras ou indisponíveis no momento da previsão. |

---

# 🧪 Engenharia de prompts e “cicatrizes”

O NotebookLM foi utilizado como ferramenta de apoio ao estudo. A construção dos prompts foi tratada como parte do processo de aprendizagem: perguntas genéricas foram refinadas para obter respostas mais específicas, contextualizadas e úteis para o TCC.

## Principais aprendizados com os prompts

### Cicatriz 1 — Perguntas muito amplas geram respostas superficiais

**Problema:** perguntar apenas “explique séries temporais” pode resultar em uma explicação extensa, porém pouco direcionada.

**Aprendizado:** delimitar o conceito, indicar o nível de profundidade e especificar a finalidade da resposta.

**Estratégia de melhoria:**

> Explique o conceito de [CONCEITO] utilizando exclusivamente as fontes fornecidas. Estruture a resposta em definição, intuição, exemplo, aplicação em previsão e limitações. Ao final, indique em qual fonte cada afirmação importante está fundamentada.

### Cicatriz 2 — Conceitos semelhantes podem ser confundidos

**Problema:** tendência, sazonalidade, ciclo e ruído possuem características diferentes, mas podem ser apresentados de forma simplificada demais.

**Aprendizado:** solicitar comparação explícita e exemplos.

**Estratégia de melhoria:**

> Compare tendência, sazonalidade, ciclo e ruído em uma tabela. Para cada conceito, apresente definição, comportamento esperado, exemplo e como ele pode ser identificado em um gráfico de série temporal.

### Cicatriz 3 — Modelo não deve ser escolhido apenas pela descrição teórica

**Problema:** conhecer ARIMA, Prophet, regressão ou outro modelo não significa que ele seja adequado para qualquer série.

**Aprendizado:** separar “como o modelo funciona” de “quando faz sentido utilizá-lo”.

**Estratégia de melhoria:**

> Explique como o modelo funciona e, separadamente, apresente as condições dos dados que favorecem ou dificultam sua utilização. Não indique um modelo como superior sem evidência experimental.

### Cicatriz 4 — Comparações precisam de critérios equivalentes

**Problema:** comparar modelos usando configurações, horizontes ou conjuntos de dados diferentes pode produzir uma conclusão enviesada.

**Aprendizado:** estabelecer uma metodologia comum de avaliação.

**Estratégia de melhoria:**

> Compare os modelos considerando exatamente o mesmo período de treino, validação e teste, o mesmo horizonte de previsão e as mesmas métricas. Diferencie claramente desempenho, complexidade, interpretabilidade e requisitos de dados.

### Cicatriz 5 — A IA deve ser tratada como apoio, não como fonte única de validação

**Problema:** uma resposta bem escrita pode ainda conter simplificações ou interpretações inadequadas.

**Aprendizado:** conferir conceitos nas fontes originais e solicitar referências.

**Estratégia de melhoria:**

> Responda utilizando somente as fontes disponibilizadas. Para cada conceito, informe a fonte correspondente. Se a informação não estiver presente nas fontes, diga explicitamente que ela não foi encontrada.

---

# 🧩 Banco de prompts reutilizáveis

Os prompts abaixo podem ser reutilizados para revisão do tema, preparação para o TCC ou exploração de novos conceitos.

## 1. Prompt de explicação conceitual

```text
Explique [CONCEITO] como se eu estivesse estudando previsão de séries temporais pela primeira vez.

Estruture em:
1. definição;
2. intuição;
3. exemplo simples;
4. importância para previsão;
5. quando utilizar;
6. limitações;
7. relação com outros conceitos.

Utilize prioritariamente as fontes fornecidas e indique as fontes utilizadas.
```

## 2. Prompt para comparação de conceitos

```text
Compare [CONCEITO A], [CONCEITO B], [CONCEITO C] e [CONCEITO D].

Monte uma tabela contendo:
- definição;
- objetivo;
- como identificar;
- exemplo;
- impacto na previsão;
- método utilizado para tratamento/análise;
- principal diferença em relação aos demais.

Não simplifique conceitos diferentes como se fossem equivalentes.
```

## 3. Prompt para estudar um capítulo

```text
Faça um guia de estudo do capítulo [NÚMERO/NOME] sobre previsão de séries temporais.

Apresente:
- conceitos fundamentais;
- conceitos que dependem de conhecimentos anteriores;
- fórmulas importantes, quando existirem;
- exemplos práticos;
- erros conceituais comuns;
- perguntas de revisão;
- relação do capítulo com modelagem preditiva.

Baseie a resposta exclusivamente nas fontes fornecidas.
```

## 4. Prompt para decomposição

```text
Explique como realizar a decomposição de uma série temporal.

Compare decomposição clássica e STL, apresentando:
- objetivo;
- componentes obtidos;
- vantagens;
- limitações;
- quando utilizar cada abordagem;
- como interpretar os componentes resultantes.
```

## 5. Prompt para ACF e PACF

```text
Explique ACF e PACF para alguém que precisa utilizar essas ferramentas na identificação de modelos ARIMA.

Mostre:
- o que cada função mede;
- diferença entre ACF e PACF;
- interpretação dos lags;
- padrões esperados em processos AR, MA e ARMA;
- limitações da identificação visual.
```

## 6. Prompt para ARIMA

```text
Explique ARIMA(p,d,q) detalhadamente.

Explique separadamente:
- componente AR;
- diferenciação;
- componente MA;
- significado de p, d e q;
- estacionariedade;
- identificação do modelo;
- diagnóstico dos resíduos;
- previsão;
- limitações.

Depois explique quando faria sentido considerar SARIMA, ARIMAX ou SARIMAX.
```

## 7. Prompt para regressão dinâmica

```text
Explique regressão dinâmica aplicada à previsão de séries temporais.

Mostre a diferença entre:
- regressão tradicional;
- regressão com defasagens;
- regressão dinâmica;
- ARIMAX/SARIMAX.

Apresente um exemplo hipotético e explique quais informações precisam estar disponíveis no momento da previsão.
```

## 8. Prompt para avaliação de modelos

```text
Explique como comparar modelos de previsão de séries temporais utilizando MAE, RMSE, MAPE, sMAPE e MASE.

Para cada métrica apresente:
- fórmula;
- interpretação;
- vantagens;
- limitações;
- situações em que pode ser inadequada.

Explique também por que a comparação deve utilizar um procedimento temporal consistente.
```

## 9. Prompt para resíduos

```text
Explique como realizar o diagnóstico dos resíduos de um modelo de previsão.

Inclua:
- média dos resíduos;
- variância;
- distribuição;
- ACF dos resíduos;
- ruído branco;
- teste de Ljung-Box;
- interpretação de resíduos ainda autocorrelacionados.

Finalize com um checklist de diagnóstico.
```

## 10. Prompt para desenho experimental

```text
Ajude a estruturar um experimento de comparação de modelos de previsão.

Considere:
- série temporal diária;
- divisão temporal entre treino, validação e teste;
- horizonte de previsão;
- walk-forward validation;
- benchmarks;
- métricas MAE, RMSE, MAPE, sMAPE e MASE;
- diagnóstico dos resíduos.

Explique quais decisões metodológicas precisam ser definidas antes de executar os modelos.
```

## 11. Prompt para análise crítica

```text
Analise a seguinte afirmação sobre previsão de séries temporais:

"[AFIRMAÇÃO]"

Classifique a afirmação como:
- correta;
- parcialmente correta;
- incorreta;
- depende do contexto.

Justifique utilizando exclusivamente as fontes fornecidas e apresente possíveis interpretações alternativas quando existirem.
```

## 12. Prompt para preparação para o TCC

```text
Relacione os conceitos estudados em previsão de séries temporais com um TCC que busca comparar modelos preditivos para métricas de marketing digital.

Não escolha o modelo por mim.

Em vez disso, apresente:
- quais características dos dados devem ser investigadas;
- quais modelos podem ser considerados;
- quais variáveis podem ser relevantes;
- quais riscos metodológicos devem ser evitados;
- como estruturar treino, validação e teste;
- como comparar os resultados de maneira justa.
```

## 13. Prompt de revisão ativa

```text
Faça uma sessão de revisão sobre previsão de séries temporais.

Apresente uma pergunta por vez, começando pelo nível básico e aumentando gradualmente a dificuldade.

Após minha resposta:
1. avalie o conteúdo;
2. indique o que está correto;
3. corrija os erros;
4. explique o conceito necessário;
5. faça uma nova pergunta relacionada.

Priorize compreensão e raciocínio, não memorização.
```

## 14. Prompt para transformar estudo em flashcards

```text
Transforme o conteúdo estudado em flashcards.

Regras:
- uma ideia por cartão;
- pergunta objetiva;
- resposta curta, mas suficiente;
- inclua conceitos, diferenças, fórmulas e interpretações;
- não crie informações que não estejam nas fontes.

Organize por dificuldade: básico, intermediário e avançado.
```

## 15. Prompt para identificar lacunas

```text
Com base no mapa de estudos de previsão de séries temporais, identifique quais assuntos ainda precisam ser estudados para que eu tenha uma visão consistente do tema.

Separe em:
- fundamentos;
- análise exploratória;
- decomposição;
- modelos;
- avaliação;
- diagnóstico;
- aplicação prática.

Para cada lacuna, explique por que ela é importante e qual conhecimento anterior devo dominar antes.
```

---

# 🔬 Relação com o TCC

O estudo de previsão de séries temporais funciona como base teórica para o desenvolvimento do TCC. A partir dele, conceitos como **dependência temporal, decomposição, sazonalidade, variáveis explicativas, modelos estatísticos, validação temporal e métricas de erro** podem ser conectados ao problema de previsão de métricas de marketing digital.

A principal contribuição deste caderno é organizar o conhecimento necessário para que a escolha e a avaliação dos modelos no TCC sejam orientadas por **características dos dados e evidências experimentais**, e não apenas pela popularidade ou complexidade de determinado algoritmo.

---

# 🗂️ Estrutura sugerida do repositório

```text
.
├── README.md
├── docs/
│   └── mapa-mental.png
├── fontes/
│   └── links.md
├── prompts/
│   └── prompts-notebooklm.md
└── estudos/
    ├── 01-introducao.md
    ├── 02-graficos-series-temporais.md
    ├── 03-decomposicao.md
    ├── 04-features.md
    ├── 05-toolbox-previsao.md
    ├── 06-previsoes-julgamento.md
    ├── 07-regressao.md
    ├── 08-suavizacao-exponencial.md
    ├── 09-arima.md
    ├── 10-regressao-dinamica.md
    ├── 11-series-hierarquicas.md
    ├── 12-metodos-avancados.md
    └── 13-questoes-praticas.md
```

---

# ✅ Checklist de aprendizagem

- [ ] Entender o que caracteriza uma série temporal
- [ ] Diferenciar tendência, sazonalidade, ciclo e ruído
- [ ] Interpretar gráficos temporais
- [ ] Entender lag e autocorrelação
- [ ] Reconhecer ruído branco
- [ ] Compreender decomposição e STL
- [ ] Conhecer features de séries temporais
- [ ] Entender benchmarks de previsão
- [ ] Conhecer modelos de regressão para previsão
- [ ] Compreender suavização exponencial
- [ ] Compreender ARIMA
- [ ] Diferenciar ARIMA, SARIMA, ARIMAX e SARIMAX
- [ ] Entender regressão dinâmica
- [ ] Conhecer séries hierárquicas
- [ ] Conhecer métodos avançados de previsão
- [ ] Saber estruturar treino, validação e teste temporal
- [ ] Entender walk-forward validation
- [ ] Avaliar previsões com métricas adequadas
- [ ] Diagnosticar resíduos
- [ ] Utilizar ACF e Ljung-Box no diagnóstico
- [ ] Saber formular prompts para estudo com IA
- [ ] Validar respostas da IA nas fontes originais

---

# 🎯 Resultado esperado

Ao final do caderno, o objetivo não é apenas memorizar diferentes modelos de previsão, mas desenvolver uma visão de **processo de modelagem de séries temporais**:

```text
Problema de negócio
       ↓
Compreensão dos dados
       ↓
Análise exploratória
       ↓
Identificação de padrões
       ↓
Transformações / features
       ↓
Escolha de modelos candidatos
       ↓
Treino e validação temporal
       ↓
Previsões
       ↓
Avaliação das métricas
       ↓
Diagnóstico dos resíduos
       ↓
Comparação dos modelos
       ↓
Interpretação e tomada de decisão
```

Esse fluxo conecta o estudo teórico realizado no caderno com a aplicação prática de previsão de séries temporais no TCC.

---

## 👩‍💻 Autoria

Caderno temático desenvolvido como parte do processo de estudo em **Ciência da Computação**, utilizando o **NotebookLM** como ferramenta de apoio à pesquisa, organização das fontes, formulação de perguntas e revisão dos conteúdos.
