# 📊 Projeto de Análise e Previsão com Séries Temporais

Com o avanço da tecnologia, houve um significativo aumento na produção de dados em todo o mundo. Paralelamente, observou-se um crescimento nas aplicações que utilizam esses dados, abrangendo diversas áreas, como saúde, indústria e monitoramento de temperatura/clima. Contudo, é comum ocorrer a perda de dados ou a presença de dados faltantes, sendo esses ausentes/faltantes originados por diversos motivos, como erros de transmissão, problemas de comunicação, defeitos nos sensores e erros humanos, constituindo um desafio para aqueles que buscam realizar previsões e análises.

O problema torna-se mais complexo e profundo quando falamos de dados faltantes em séries temporais multivariadas, devido a fatores como sazonalidade, tendência, ruído branco, entre outros, que são elementos importantes a serem considerados na escolha de um método de imputação apropriado (Luo et al., 2018).

Em relação às séries temporais, é importante destacar que estas podem apresentar tendências, manifestando-se com crescimento ou decréscimo ao longo do tempo, de forma linear ou não. Além disso, podem exibir sazonalidades, caracterizadas por fatores sazonais fixos e com frequência conhecida. Também é possível que as séries temporais apresentem dados cíclicos, os quais não seguem uma frequência definida. Uma maneira de visualizar a tendência e a sazonalidade em séries temporais é por meio de funções de autocorrelação (conforme mencionado por Luo et al., 2018) e outras técnicas de análise específicas.

As séries temporais discretas são observações feitas em intervalos de tempo fixos, em que o intervalo de observações, conhecido como \(t\), pertence a um conjunto discreto. Enquanto as séries temporais contínuas são observações obtidas continuamente através de algum intervalo no tempo, em que \(T=[0,1]\).

De maneira geral, podemos dizer que o que é feito é observar e analisar um conjunto de dados durante um tempo.

As séries temporais podem ser sazonais, ter tendência e podem ter ambos ao mesmo tempo. A tendência de uma série temporal indica seu comportamento a longo prazo, se ela está estável, crescendo ou decrescendo. Podemos descrever um modelo com tendência em \(X_t = M_t + Y_t\), em que \(M_t\) é o componente de tendência e pode ser estimado através do método dos mínimos quadrados ou OLS, podendo ser visto como \(M_t = a_0 + a_1 \cdot t + a_2 \cdot t^2\). Os valores de \(a\) são ajustados para minimizar a função de soma de todos os valores \(N\) no tempo 1 \((X_t - M_t)^2\). A tendência linear é uma linha reta que sobe ou desce, a tendência constante é uma linha reta na horizontal, enquanto a tendência quadrática indica uma curva subindo ou descendo.

Dizemos que temos a sazonalidade que ocorre em intervalos de tempo mais fáceis de serem previstos, como \(X_t = S_t + Y_t\), em que \(S_t\) é o componente de sazonalidade, resultando em uma função periódica que pode ser obtida através da soma das ondas senoidais.

Já aqueles que possuem movimento cíclico tendem a ter intervalos de tempo irregulares, sendo o ciclo o aumento ou redução de frequência sem intervalos fixos. Alguns exemplos são as crises econômicas.

Erros são os restos/sobras que existem junto às tendências e sazonalidades, sendo dados que ocorrem por causas aleatórias e não são explicados na série temporal, matematicamente.

Conceitos de séries temporais:
- Séries estacionárias: a média e a variância se mantêm constantes durante o tempo. Em princípio, séries com tendência e sazonalidade não são estacionárias, enquanto uma série temporal sazonal pode ser estacionária.

Existem testes estatísticos para verificar a estacionariedade de uma série, entre eles:

- **Dickey-Fuller (ADF):** Testa a presença de raiz unitária. Se rejeita a hipótese nula (de não-estacionariedade), a série é estacionária.
- **KPSS (Kwiatkowski-Phillips-Schmidt-Shin):** Ao contrário do ADF, sua hipótese nula é que a série **é estacionária**.
- **Phillips-Perron (PP):** Variante mais robusta do teste Dickey-Fuller, ajustando para heterocedasticidade e autocorrelação nos resíduos.


Tipos de modelos:
- Modelos univariados incluem os modelos que se baseiam em uma única série temporal histórica, como o ARIMA e modelos univariados de Box e Jenkins de 1970.

O modelo ARIMA é um modelo autorregressivo integrado de médias móveis.


## 🧠 Conceitos Fundamentais

### Modelos Clássicos
- AR, MA, ARMA
- ARIMA, SARIMA, SARIMAX
- Representação espectral, filtros lineares
- Estimação no tempo e na frequência (Fourier, periodograma)

### Redes Neurais e Modelos Profundos
- LSTM, RNN, MLP
- Arquiteturas híbridas (ex: SARIMA + LSTM)



## 🧠 Conceitos Fundamentais de Séries Temporais

Antes de mergulharmos nos modelos e na metodologia, é crucial entender os conceitos fundamentais que permeiam a análise de séries temporais.

## O Que São Séries Temporais?

Uma **série temporal** é uma sequência de dados coletados e indexados ao longo do tempo, organizados em ordem cronológica. Cada ponto na série corresponde a uma observação realizada em um instante ou período específico.

Esses dados podem representar uma vasta gama de fenômenos que evoluem com o tempo, incluindo:

* **Economia e Finanças:** Preços de ações, taxas de câmbio, inflação, Produto Interno Bruto (PIB), vendas de varejo.
* **Ciências Naturais:** Temperatura diária, precipitação pluviométrica, níveis de rios, atividade solar.
* **Engenharia:** Tráfego de rede, consumo de energia, leituras de sensores em processos industriais.
* **Marketing e Vendas:** Demanda por produtos, visitas a websites, engajamento em redes sociais.
* **Saúde:** Número de casos de doenças ao longo do tempo, batimentos cardíacos monitorados continuamente.

---

### Tipos de Séries Temporais

As séries temporais podem ser classificadas principalmente em duas categorias, dependendo da natureza da sua indexação temporal:

* **Séries Temporais Discretas:** São sequências de observações realizadas em **intervalos de tempo fixos e distintos**. O conjunto de instantes de observação ($t$) pertence a um conjunto discreto, como dias, semanas, meses, anos, etc. Exemplos incluem o preço de uma ação no fechamento de cada dia ou a média mensal de temperatura.

* **Séries Temporais Contínuas:** Representam observações que são obtidas de forma **contínua** ao longo de um intervalo de tempo. Teoricamente, podemos ter uma observação para cada instante dentro de um dado período, como a leitura contínua da temperatura de um forno ou o monitoramento constante de um eletrocardiograma. Matematicamente, o índice de tempo $T$ pertence a um intervalo contínuo, como $[0, 1]$ (representando um intervalo normalizado) ou um intervalo real $[a, b]$.

É importante notar que, na prática, mesmo fenômenos contínuos são frequentemente amostrados e analisados como séries temporais discretas devido às limitações de coleta e armazenamento de dados.

### Componentes de Séries Temporais

A análise de séries temporais frequentemente envolve a decomposição dos dados em seus componentes constituintes, que ajudam a entender os padrões subjacentes e a realizar previsões. Os principais componentes são:

* **Tendência (Trend):** Representa a direção geral de longo prazo da série temporal. Indica se os dados estão consistentemente aumentando, diminuindo ou permanecendo estáveis ao longo do tempo. A tendência pode ser linear, não linear (por exemplo, quadrática, exponencial) ou até mesmo mudar de direção ao longo da série.

    Podemos modelar uma tendência ($m_t$) de diversas formas. Uma **tendência linear** pode ser expressa como:
    $$m_t = a_0 + a_1 t$$
    onde $a_0$ é o intercepto e $a_1$ é a inclinação, indicando a taxa de crescimento ou decrescimento.

    Uma **tendência polinomial de grau 2 (quadrática)** é dada por:
    $$m_t = a_0 + a_1 t + a_2 t^2$$
    que pode capturar curvaturas na tendência.

    Os coeficientes ($a_0, a_1, a_2, ...$) são geralmente estimados utilizando o método dos **Mínimos Quadrados Ordinários (OLS - Ordinary Least Squares)**, que busca minimizar a soma dos quadrados das diferenças entre os valores observados ($x_t$) e a tendência modelada ($m_t$):
    $$\min_{a_0, a_1, ...} \sum_{t=1}^{N} (x_t - m_t)^2$$
    onde $N$ é o número total de observações.

* **Sazonalidade (Seasonality):** Refere-se a padrões que se repetem em intervalos de tempo fixos e conhecidos, geralmente dentro de um ano. Exemplos comuns incluem o aumento nas vendas de sorvetes no verão ou o pico de compras no varejo durante as festas de fim de ano. A sazonalidade é periódica e pode ser modelada utilizando funções periódicas, como a soma de ondas senoidais (como mencionado no material da UFPE).

    Um modelo simples com componente sazonal ($s_t$) pode ser:
    $$x_t = s_t + Y_t$$
    onde $Y_t$ representa os outros componentes (tendência, ciclo, erro). A componente sazonal $s_t$ é tal que $s_t = s_{t+p}$, onde $p$ é o período da sazonalidade (por exemplo, $p=12$ para sazonalidade mensal em dados anuais).

* **Ciclos (Cyclical Patterns):** Representam flutuações de longo prazo na série temporal, com duração geralmente maior que um ano. Ao contrário da sazonalidade, os ciclos não têm uma frequência fixa e seus intervalos de tempo são irregulares. Exemplos clássicos são os ciclos econômicos de expansão e recessão.

* **Ruído (Erro ou Resíduo):** É o componente aleatório da série temporal que não pode ser explicado pelos outros componentes (tendência, sazonalidade, ciclo). Representa a variabilidade não sistemática ou eventos imprevisíveis que afetam os dados.

Um modelo aditivo comum para decompor uma série temporal é:
$$x_t = Tendência_t + Sazonalidade_t + Ciclo_t + Ruído_t$$
Ou, de forma mais simplificada:

$$x_t = T_t + S_t + C_t + \epsilon_t$$

### Conceitos Importantes em Séries Temporais

* **Estacionariedade:** Uma série temporal é considerada **estacionária** se suas propriedades estatísticas fundamentais, como a média e a variância, permanecem constantes ao longo do tempo. Além disso, a autocovariância entre dois pontos da série depende apenas da distância (lag) entre eles, e não do tempo absoluto em que as observações foram feitas.

    Em princípio, séries temporais que apresentam tendência ou sazonalidade **não são estacionárias**, pois sua média (devido à tendência) ou sua média em certos períodos (devido à sazonalidade) variam com o tempo. No entanto, uma série temporal com sazonalidade pode se tornar estacionária após a remoção do componente sazonal (dessazonalização).

* **Testes de Estacionariedade:** Existem testes estatísticos formais para verificar se uma série temporal é estacionária. Alguns dos testes mais comuns incluem:
    * **Teste de Dickey-Fuller (e sua versão aumentada, ADF):** Testa a presença de uma raiz unitária na série, cuja presença sugere não estacionariedade.
    * **Teste KPSS (Kwiatkowski-Phillips-Schmidt-Shin):** Testa a hipótese nula de estacionariedade em torno de uma média ou de uma tendência determinística.
    * **Teste de Phillips-Perron:** Similar ao ADF, mas com uma abordagem diferente para lidar com a autocorrelação nos erros.

A compreensão desses conceitos é fundamental para a análise e modelagem eficaz de séries temporais, permitindo a realização de previsões e a extração de insights significativos dos dados.

### Conceitos Estatísticos Fundamentais
* **Processos Estocásticos e Séries Temporais:** Um processo estocástico é uma sequência de variáveis aleatórias indexadas pelo tempo. Uma série temporal é a realização de um processo estocástico.
* **Estacionariedade:** Propriedade onde as características estatísticas (média, variância, autocovariância) não mudam ao longo do tempo. Séries com tendência ou sazonalidade geralmente não são estacionárias.
* **Função de Autocovariância:** Mede a correlação entre valores da série em diferentes pontos no tempo (lags).
* **Espectro:** Representação da distribuição da variância da série em diferentes frequências.

---

# 📈 Análise de Séries Temporais: Guia Completo de Autocorrelação (ACF) e Correlação Parcial (PACF)

A análise de séries temporais é um campo vital para a compreensão e previsão de fenômenos que evoluem ao longo do tempo. Uma das características mais fundamentais e informativas de uma série temporal é a sua **autocorrelação**, que revela a estrutura de dependência interna entre seus valores em diferentes pontos no tempo. Este guia detalha o que são Autocorrelação (ACF) e Correlação Parcial (PACF), como interpretá-los e suas aplicações práticas na modelagem.

---

## 📌 1. O Que é Autocorrelação?

A autocorrelação mede a **correlação linear** de uma variável com ela mesma em diferentes pontos no tempo. Ela nos fornece uma medida adimensional da associação linear entre os valores atuais de uma série e seus valores passados (defasados).

### ✅ **1.1. Coeficiente de Autocorrelação**

No eixo Y de um gráfico de autocorrelação, temos o **coeficiente de correlação**, que é uma medida padronizada e varia entre -1 e 1:

* **Coeficiente = 0:** Indica que não há correlação linear entre os valores da série e seus valores defasados. Ou seja, as variáveis são independentes linearmente para aquela defasagem.
* **Coeficiente > 0 (próximo a +1):** Indica uma **correlação positiva**. Se o valor atual da série aumenta, o valor defasado correspondente também tende a aumentar.
* **Coeficiente < 0 (próximo a -1):** Indica uma **correlação negativa**. Se o valor atual da série aumenta, o valor defasado correspondente tende a diminuir.

É importante ressaltar que a presença de correlação pode variar significativamente entre diferentes defasagens. Um atraso pode não apresentar correlação, enquanto atrasos maiores podem revelar uma dependência estatisticamente significativa. Os gráficos de autocorrelação nos ajudam a visualizar esses padrões.

### 🔬 **1.2. Fórmulas Fundamentais**

A compreensão das fórmulas subjacentes ao cálculo da autocorrelação e autocovariância é essencial:

* **Coeficiente de Autocorrelação $r_k$:**
    Mede a relação entre $y_t$ (valor atual) e $y_{t-k}$ (valor defasado em $k$ períodos). Para cada defasagem $k$, $r_k$ é o coeficiente de correlação de Pearson.

    $$r_k = \frac{\sum_{t=k+1}^{T} (y_t - \bar{y})(y_{t-k} - \bar{y})}{\sum_{t=1}^{T} (y_t - \bar{y})^2}$$

    Onde:
    * $T$: É o comprimento da série temporal.
    * $\bar{y}$: É a média da série.
    * $k$: É a defasagem (lag).

    Os coeficientes de autocorrelação para diferentes valores de $k$ compõem a **Função de Autocorrelação (ACF)**.

* **Autocovariância $\gamma_k$:**
    Mede o grau de dependência linear que uma observação $Z_t$ possui com ela mesma defasada em $k$ períodos.

    $$\gamma_k = \text{Cov}(Z_t, Z_{t-k}) = E[(Z_t - \mu)(Z_{t-k} - \mu)]$$

    Onde:
    * $\mu$: É a média da série.

    A autocorrelação depende apenas do intervalo entre as medidas ($h$ ou $k$), não do ponto específico no tempo.

---

## 🎯 2. Defasagem (Lag)

Uma **defasagem (lag)** representa o número de períodos de tempo que separam duas observações em uma série temporal.

* **Exemplo:** Se você está analisando dados mensais:
    * **Lag 1:** Relação entre o mês atual e o mês anterior.
    * **Lag 2:** Relação entre o mês atual e dois meses atrás.
    * E assim por diante.

---

## 📈 3. Autocorrelação (ACF) vs. Correlação Parcial (PACF)

Embora ambas as funções analisem a dependência da série com seus próprios valores passados, elas o fazem de maneiras distintas, fornecendo informações complementares.

### ✅ **3.1. Função de Autocorrelação (ACF)**

* **Mede:** A correlação entre uma variável ($X_t$) e seus valores defasados ($X_{t-k}$), abrangendo **toda a correlação** — tanto a direta quanto a indireta (aquela que é transmitida através de lags intermediários).
* **Intuição:** Pense na ACF como capturando a "teia completa" de influências passadas, onde a correlação no lag 5, por exemplo, pode ser influenciada por correlações nos lags 1, 2, 3 e 4.

### ✅ **3.2. Função de Autocorrelação Parcial (PACF)**

* **Mede:** A correlação **direta** entre uma variável ($X_t$) e seus valores defasados ($X_{t-k}$), **após remover o efeito** de todas as defasagens intermediárias ($X_{t-1}, X_{t-2}, \dots, X_{t-(k-1)}$).
* **Intuição:** A PACF "limpa" essa teia, isolando a influência direta de cada lag. Por exemplo, a PACF de lag 2 mede a correlação entre $X_t$ e $X_{t-2}$ *somente* aquela não explicada pela influência de $X_{t-1}$.

---

## 🧪 4. Como Interpretar os Gráficos ACF e PACF

Os gráficos de ACF e PACF são visualizações cruciais para a análise. Eles apresentam os coeficientes de correlação (ou correlação parcial) no **Eixo Y** e as defasagens (lags) no **Eixo X**.

### ✅ **4.1. Faixa Azul (Intervalo de Confiança)**

* A **faixa azul** que circunda o zero nos gráficos representa o **intervalo de confiança** (tipicamente de 95%).
* **Significância Estatística:**
    * Se uma barra (pico) de correlação **ultrapassa** essa faixa, o coeficiente de correlação para aquela defasagem é considerado **estatisticamente significativo**, ou seja, é improvável que seja zero por acaso.
    * Se os picos **ficam dentro** da faixa azul, a correlação para aquela defasagem **não é estatisticamente significativa**. Isso sugere que a correlação observada pode ser apenas ruído aleatório e não uma dependência real da série.

### 🧠 **4.2. Comportamento e Precisão**

* A precisão da autocorrelação tende a diminuir à medida que o número de defasagens (lags) aumenta, pois há menos pares de dados para calcular a correlação em defasagens maiores.

---

## ⚪ 5. Ruído Branco

Um conceito fundamental na análise de séries temporais é o de **ruído branco**.

* **Definição:** Uma série de **ruído branco** é caracterizada por valores que são independentes e identicamente distribuídos, o que significa que não há autocorrelação linear em nenhum lag.
* **Interpretação nos Gráficos:**
    * Para uma série de ruído branco, espera-se que **todos (ou quase todos)** os coeficientes de autocorrelação (tanto na ACF quanto na PACF) estejam **dentro da faixa azul** para todos os lags.
    * Os valores dos coeficientes serão próximos de zero, mas não exatamente zero devido às variações aleatórias inerentes aos dados.
* **Regra Prática:** Espera-se que aproximadamente 95% dos picos da ACF e PACF caiam dentro da faixa de $\pm 2/\sqrt{T}$, onde $T$ é o tamanho da série temporal.

---

Recursos de defasagem e recursos de janela
Os recursos de defasagem são valores em intervalos de tempo anteriores que são considerados úteis porque são criados com base na suposição de que o que aconteceu no passado pode influenciar ou conter um tipo de informação intrínseca sobre o futuro. Por exemplo, pode ser vantajoso gerar recursos para vendas que ocorreram em dias anteriores às 16h00 se você quiser prever vendas semelhantes às 16h00 do dia seguinte.

Uma categoria interessante de recursos de defasagem é chamada de recursos de defasagem aninhados. Para criar recursos de defasagem aninhados, os cientistas de dados devem identificar um período de tempo fixo no passado e, em seguida, agrupar os valores dos recursos por esse período de tempo - por exemplo, o número de itens vendidos nas duas horas anteriores, nos três dias anteriores e na semana anterior.
A operação de adicionar recursos de defasagem é chamada de método de janela deslizante ou recursos de janela. O exemplo acima mostra como aplicar um método de janela deslizante com uma largura de janela de oito. Os recursos de janela são um resumo dos valores em uma janela fixa de intervalos de tempo anteriores.

Dependendo do cenário da série temporal, você pode expandir a largura da janela e incluir mais recursos defasados. Uma pergunta comum que os cientistas de dados fazem antes de realizar a operação de adicionar recursos de defasagem é o tamanho da janela. Uma boa abordagem seria criar uma série de diferentes larguras de janela e, alternativamente, adicioná-las e removê-las do conjunto de dados para ver qual delas tem um efeito positivo mais evidente no desempenho do modelo.




## 📚 6. Aplicações Práticas na Seleção de Modelos ARIMA

Os gráficos ACF e PACF são as ferramentas primárias e mais intuitivas para determinar os parâmetros $p$, $d$, e $q$ de um modelo ARIMA (AutoRegressive Integrated Moving Average), ou seus análogos sazonais para SARIMA.

1.  ### ✅ **Estacionariedade e o Parâmetro `d` (Ordem de Diferenciação)**
    * Antes de analisar os gráficos ACF e PACF para $p$ e $q$, é crucial que a série temporal seja **estacionária** (média, variância e autocovariância constantes ao longo do tempo).
    * Se a série não for estacionária (apresentar tendência, sazonalidade, etc.), ela precisa ser **diferenciada**. O número de vezes que a série é diferenciada para se tornar estacionária define o parâmetro `d` do ARIMA.
    * Os gráficos ACF e PACF são então analisados na série *diferenciada* para identificar $p$ e $q$.

2.  ### ✅ **Análise dos Gráficos para `p` e `q`**

    * **PACF para $p$ (Ordem Autorregressiva - AR):**
        * O parâmetro $p$ está associado aos termos autorregressivos (AR) do modelo, que utilizam observações passadas da própria série.
        * Na PACF, procure um "corte" abrupto (as barras significativas tornam-se não significativas ou caem dentro da faixa azul) após um certo número de lags.
        * O número do último lag significativo antes do corte sugere o valor de $p$.
        * **Exemplo:** Se a PACF tem picos significativos em lags 1, 2, mas em 3 e além eles são insignificantes, isso sugere $p=2$.

    * **ACF para $q$ (Ordem da Média Móvel - MA):**
        * O parâmetro $q$ está associado aos termos de média móvel (MA) do modelo, que utilizam erros passados (ruído branco) da previsão.
        * Na ACF, procure um "corte" abrupto (as barras significativas tornam-se não significativas ou caem dentro da faixa azul) após um certo número de lags.
        * O número do último lag significativo antes do corte sugere o valor de $q$.
        * **Exemplo:** Se a ACF tem um pico significativo apenas em lag 1, mas em 2 e além os picos são insignificantes, isso sugere $q=1$.

3.  ### ✅ **Estimação e Avaliação do Modelo**

    * Após a identificação inicial de $p, d, q$, o modelo ARIMA é estimado.
    * Utilizam-se métodos como a **Estimativa de Máxima Verossimilhança (MLE)** ou critérios de informação como **AIC (Akaike Information Criterion)** e **BIC (Bayesian Information Criterion)** para refinar a escolha dos parâmetros e comparar diferentes modelos.

4.  ### ✅ **Validação do Modelo**

    * É crucial testar e validar o modelo final. Isso é feito principalmente através da análise dos **resíduos do modelo**.
    * Testes de diagnóstico, como o **Teste de Ljung-Box**, são usados para verificar se os resíduos do modelo são ruído branco. Se os resíduos não forem ruído branco, isso indica que o modelo não capturou toda a estrutura de dependência da série, e uma nova otimização dos parâmetros pode ser necessária.

---

### ✅ **Conclusão**

Os gráficos ACF e PACF são as **ferramentas diagnósticas mais fundamentais e poderosas** na caixa de ferramentas de um analista de séries temporais. Eles não apenas revelam a quantidade de dependência linear entre uma observação e seus valores passados, mas também a natureza direta dessa dependência. Dominar a interpretação desses gráficos é essencial para identificar o tipo e a ordem do modelo ARIMA ideal e para validar sua adequação.

---
### Modelos Clássicos
* **Modelos AR (Autoregressivos):** Utilizam valores passados da própria série para prever o valor futuro.
* **Modelos MA (Médias Móveis):** Utilizam erros de previsão passados para prever o valor futuro.
* **Modelos ARMA (Autoregressive Moving Average):** Combinam componentes AR e MA.
* **Modelos ARIMA (Autoregressive Integrated Moving Average):** Estendem ARMA para séries não estacionárias através da diferenciação (componente "Integrated").
    * **O que é o modelo ARIMA:** Combina AutoRegressão (AR), Integração (I - para tornar a série estacionária por diferenciação), e Média Móvel (MA).
* **Modelos SARIMA (Seasonal ARIMA):** Extensão do ARIMA para dados com sazonalidade, incorporando componentes sazonais. É um modelo multiplicativo que considera variações sazonais e não sazonais.
* **Modelos SARIMAX:** Extensão do SARIMA que inclui variáveis exógenas (preditores externos).
* **Representação Espectral e Filtros Lineares:** Análise da série no domínio da frequência e aplicação de filtros para extrair ou remover certas componentes.
* **Estimação no Tempo e na Frequência:**
    * **Domínio do Tempo:** Estimação de parâmetros dos modelos ARMA/ARIMA usando métodos como máxima verossimilhança.
    * **Domínio da Frequência:** Utilização da Transformada de Fourier e do periodograma para analisar a estrutura espectral da série e estimar componentes periódicas.

### Modelos de Aprendizado de Máquina
* **SVM (Support Vector Machines):** Algoritmo supervisionado para classificação e regressão. Em séries temporais, pode ser usado para prever o valor futuro como um problema de regressão.
    * Utiliza um hiperplano ideal para maximizar a margem entre classes (em classificação) ou ajustar uma função para prever valores (em regressão).
    * **Linear SVMs:** Adequadas para dados linearmente separáveis.
    * **Kernel Trick:** Permite lidar com dados não linearmente separáveis, transformando-os em espaços de maior dimensão.
    * **Decision Boundary:** A superfície que separa as diferentes classes (em classificação).
* **Redes Neurais e Modelos Profundos:**
    * **MLP (Multilayer Perceptron):** Redes neurais feedforward básicas.
    * **RNN (Redes Neurais Recorrentes):** Projetadas para processar dados sequenciais, utilizando loops para manter informações de passos anteriores.
        * **O que são RNNs:** Usam loops para persistir informações ao longo da sequência, tornando-as adequadas para dados sequenciais e séries temporais.
        * Arquitetura básica com entrada $x^{(t)}$, estado escondido $h^{(t)}$, e pesos $U, W, V$ compartilhados ao longo do tempo.
        * $h^{(t)} = f(U x^{(t)} + W h^{(t-1)})$, onde $f$ é uma função de ativação não linear (tanh, ReLU).
    * **LSTM (Long Short-Term Memory):** Um tipo de RNN que utiliza mecanismos de gating para lidar com dependências de longo prazo e superar o problema do vanishing/exploding gradient.
        * **O que é LSTM:** Uma RNN avançada que usa backpropagation através do tempo e células de memória para aprender dependências de longo prazo em dados sequenciais, mitigando os problemas de gradientes.
        * **Problema do Vanishing/Exploding Gradient:** Ocorre durante o backpropagation em redes profundas, onde os gradientes podem diminuir ou aumentar exponencialmente, dificultando o aprendizado.
* **Arquiteturas Híbridas:** Combinação de diferentes modelos (estatísticos e de aprendizado de máquina) para aproveitar seus pontos fortes (ex: SARIMA + LSTM).

## 🤖 Otimização de Modelos

### Algoritmos Evolutivos
Utilização de algoritmos de otimização para encontrar os melhores hiperparâmetros ou arquiteturas de modelos:
* **PSO (Particle Swarm Optimization):** Algoritmo de otimização inspirado no comportamento social de pássaros ou peixes, utilizando um enxame de partículas que exploram o espaço de busca.

## 🔬 Metodologia Proposta

### Objetivo Geral
Avaliar e comparar diferentes modelos de previsão em séries temporais com foco em desempenho, robustez e eficiência computacional.

### Etapas
1.  **Contextualização do Problema:** Definição clara do problema de previsão a ser abordado e sua relevância.
2.  **Objetivos Geral e Específicos:** Detalhamento do objetivo principal e dos objetivos menores que o sustentam.
3.  **Trabalhos Relacionados:** Revisão da literatura existente sobre o problema e as abordagens de solução.
4.  **Perguntas de Pesquisa:** Formulação das questões que o projeto busca responder.
5.  **Metodologia Proposta:** Descrição detalhada dos modelos e técnicas que serão utilizados.
6.  **Metodologia Experimental:**
    * **Arquitetura Utilizada:** Especificação das arquiteturas dos modelos implementados (ex: número de camadas LSTM, ordem ARIMA).
    * **Organização do Treinamento/Teste:** Como os dados serão divididos para treinamento, validação e teste.
    * **Hiperparâmetros e Otimizações:** Detalhes dos hiperparâmetros dos modelos e as técnicas de otimização utilizadas (ex: otimizadores, funções de perda, taxas de aprendizado).
    * **Métricas Utilizadas:** Definição das métricas de avaliação de desempenho (ex: MSE, RMSE, MAE, MAPE) com suas fórmulas e possíveis representações gráficas.
    * **Comparação de Desempenho:** Estratégia para comparar o desempenho dos diferentes modelos em termos de tempo de treinamento, erro de previsão e visualização dos resultados.

# 📊 Análise e Modelagem de Séries Temporais

Claro! Aqui está o seu conteúdo reorganizado e estruturado em um formato de Markdown mais limpo, com títulos hierárquicos consistentes, separação clara entre seções e uso padronizado de ícones e tópicos:

---

# 📊 Análise e Modelagem de Séries Temporais

Perfeito, você listou diversas etapas importantes de uma pipeline completa de **modelagem e previsão de séries temporais**. Abaixo, reorganizei esse conteúdo em formato de **checklist estruturado em Markdown**, com categorias claras para facilitar a leitura, entendimento e execução.

---

# 📊 Pipeline Completo para Modelagem de Séries Temporais

## 1. 📥 Carregamento e Limpeza dos Dados

* [ ] Carregar os dados
* [ ] **Remover colunas não pertinentes**
* [ ] **Remover linhas duplicadas**
* [ ] Converter colunas de data para `datetime`
* [ ] Definir coluna de data como **índice** e garantir **ordem cronológica**

---

## 2. 🔍 Análise Exploratória (EDA)

* [ ] Verificar **correlação entre variáveis** (caso multivariada) → `heatmap`
* [ ] Verificar **comportamento de momentum**
* [ ] Analisar presença de **white noise** (ruído branco)
* [ ] Realizar **decomposição da série**

  * [ ] Estratégia de decomposição (Ex: **exponencial**)
  * [ ] Visualizar **tendência** e **sazonalidade**
* [ ] Verificar e **interpolar dados faltantes**
* [ ] Analisar **estacionalidade** com:

  * [ ] **ACF (Função de Autocorrelação)**
  * [ ] **PACF (Autocorrelação Parcial)**
* [ ] Aplicar **diferenciação** caso a série não seja estacionária

---

## 3. 🧹 Pré-processamento e Transformações

* [ ] Realizar **normalização** dos dados (MinMax, Z-score etc.)
* [ ] Criar **janelas deslizantes** para regressão:

  * [ ] Para o conjunto de **treinamento**
  * [ ] Para o conjunto de **teste**
* [ ] Separar **20% do treino para validação**
* [ ] Selecionar **lags mais relevantes** com base em análise estatística ou feature importance

---

## 4. 📈 Treinamento de Modelos

* [ ] Ajustar apenas com o **conjunto de treinamento**
* [ ] Executar função de modelagem com os **parâmetros selecionados**
* [ ] Treinar e ajustar o modelo (ex: **ARIMA**)

  * [ ] Fit do modelo ARIMA
  * [ ] Escolha dos melhores parâmetros (AIC, BIC, grid search)
  * [ ] Previsão com o modelo ajustado
* [ ] Avaliar resíduos:

  * [ ] Plotar resíduos
  * [ ] Verificar se os resíduos são ruído branco
  * [ ] Avaliar previsões no conjunto de validação/teste

---

## 5. 🧪 Avaliação e Validação

* [ ] Avaliar previsões com métricas:

  * RMSE, MAE, MAPE, etc.
* [ ] Validar o modelo no conjunto de validação
* [ ] Confirmar que os resíduos estão centrados e sem autocorrelação

---

## 6. 🔗 Combinação de Modelos (Híbridos)

* [ ] Testar combinação de modelos:

  * **Modelo de ponderação**
  * **Método de fusão**
  * **KNN para combinação**
  * **Combinação ponderada (PTI?)**
* [ ] Estratégias de seleção dinâmica:

  * **Dynamic Selection**
  * **Oracle Selection**
  * **Worst Selection**
* [ ] Avaliar se a combinação melhora os resultados

---

## 7. 🧾 Considerações Finais

* O **resíduo** é a diferença entre o valor real e o previsto pelo modelo

  * Avaliar no conjunto de **treinamento**
  * Avaliar no conjunto de **teste**

o residuo é a diferença entre o valore real e o valor previsto pelo modelo X(arima)
isso no conjunto de treinamento
o residuo é a diferença entre o valore real e o valor previsto pelo modelo X(arima)

---

## 📈 Análise de Estacionariedade

### 🔬 Teste de Dickey-Fuller Aumentado (ADF)

O **ADF** verifica a presença de **raiz unitária**, ou seja, se a série é **não-estacionária**.

#### 🧪 Hipóteses:

* **H₀ (nula):** A série é **não-estacionária**
* **H₁ (alternativa):** A série é **estacionária**

#### 📊 Interpretação:

* **p-valor < 0.05:** Rejeita-se H₀ → Série **estacionária**
* **p-valor ≥ 0.05:** Falha em rejeitar H₀ → Série **não-estacionária**

### 🧪 Exemplo de Código com ADF

```python
from statsmodels.tsa.stattools import adfuller
import pandas as pd
import os

caminho = 'caminho_para_sua_pasta/Pernambuco'
resultados_adf = []

for arquivo in os.listdir(caminho):
    if arquivo.endswith('.csv'):
        df = pd.read_csv(os.path.join(caminho, arquivo))

        if df.shape[1] >= 2:
            nome_serie = arquivo.split('.')[0]
            serie = df.iloc[:, 1].dropna()

            try:
                adf_result = adfuller(serie)
                resultados_adf.append({
                    'arquivo': nome_serie,
                    'ADF Statistic': adf_result[0],
                    'p-value': adf_result[1],
                    'lags used': adf_result[2],
                    'nobs': adf_result[3],
                    'critical value (1%)': adf_result[4]['1%'],
                    'critical value (5%)': adf_result[4]['5%'],
                    'critical value (10%)': adf_result[4]['10%'],
                    'conclusão': 'Estacionária' if adf_result[1] < 0.05 else 'Não estacionária'
                })
            except Exception as e:
                print(f"Erro ao processar {nome_serie}: {e}")

df_resultados_adf = pd.DataFrame(resultados_adf)
print(df_resultados_adf)
```

---

# 📚 Modelos de Séries Temporais

## 📉 Modelos Clássicos

### 🔹 AR, MA, ARMA, ARIMA e Extensões

* **AR (Autoregressivo):** Usa valores passados para prever futuros.
* **MA (Média Móvel):** Usa erros de previsão passados.
* **ARMA:** Combina AR e MA.
* **ARIMA:** Usa diferenciação para lidar com não-estacionariedade.
* **SARIMA:** Extensão do ARIMA para sazonalidade.
* **SARIMAX:** Inclui variáveis exógenas (preditores externos).

### 🔹 Domínios de Estimação

* **Domínio do Tempo:** Estimação por máxima verossimilhança (ex: modelos ARIMA).
* **Domínio da Frequência:** Análise espectral com Transformada de Fourier, periodograma e filtros.

---

## 🤖 Modelos de Aprendizado de Máquina

### 🔹 SVM (Support Vector Machines)

* Usado para classificação e **regressão** em séries temporais.
* **Linear SVM:** Para dados linearmente separáveis.
* **Kernel Trick:** Para dados não lineares.
* **Decision Boundary:** Superfície que separa classes ou define função de regressão.

### 🔹 Redes Neurais

* **MLP:** Feedforward com múltiplas camadas.

* **RNN:** Redes com memória temporal:

  * Estado oculto: \$h^{(t)} = f(Ux^{(t)} + Wh^{(t-1)})\$
  * Funções de ativação: `tanh`, `ReLU`

* **LSTM (Long Short-Term Memory):**

  * Variante de RNN com mecanismos de memória.
  * Lida com **dependências de longo prazo**
  * Resolve problemas de **vanishing/exploding gradients**

### 🔹 Arquiteturas Híbridas

* Exemplo: **SARIMA + LSTM**
* Combinam pontos fortes de modelos estatísticos e redes neurais

---

# 🚀 Otimização de Modelos

## 🔸 Algoritmos Evolutivos

### PSO (Particle Swarm Optimization)

* Inspirado em enxames (pássaros, peixes)
* Cada partícula busca a melhor solução
* Útil para otimizar hiperparâmetros (ex: redes, SVM, ARIMA)

---

# 🧪 Metodologia Proposta

## 🎯 Objetivo Geral

Avaliar e comparar diferentes modelos de previsão em séries temporais quanto a:

* Desempenho
* Robustez
* Eficiência computacional

## 🧱 Etapas do Projeto

1. **Contextualização do Problema**
2. **Objetivos Geral e Específicos**
3. **Trabalhos Relacionados**
4. **Perguntas de Pesquisa**
5. **Metodologia Proposta**
6. **Metodologia Experimental**

   * Arquiteturas dos modelos (ex: ordem do ARIMA, número de camadas LSTM)
   * Estratégia de treino/teste
   * Escolha de hiperparâmetros e otimizadores
   * Métricas (ex: MSE, RMSE, MAE, MAPE)
   * Comparação de desempenho (gráficos, tabelas, tempo de execução)

---


## 📈 Análise de Estacionariedade com Teste de Dickey-Fuller Aumentado (ADF)

Ao trabalhar com séries temporais, um passo essencial é verificar se a série é **estacionária**. Modelos como **ARIMA** exigem que a série seja estacionária — isto é, que suas propriedades estatísticas como **média**, **variância** e **autocorrelação** não mudem ao longo do tempo.

### 🔍 Entendendo o Teste ADF

O **ADF (Augmented Dickey-Fuller)** é um teste estatístico que verifica a presença de uma **raiz unitária**, ou seja, se a série é **não-estacionária**.

#### 🧪 Hipóteses do Teste:

- **H₀ (nula):** A série é **não-estacionária** (possui raiz unitária).
- **H₁ (alternativa):** A série é **estacionária** (não possui raiz unitária).

#### 📊 Interpretação do p-valor:

- Se **p-valor < 0.05** (nível de significância comum), **rejeitamos H₀** → A série é **estacionária**.
- Se **p-valor ≥ 0.05**, **falhamos em rejeitar H₀** → A série é **não-estacionária**.

### 🧪 Aplicação do Teste ADF em Vários Arquivos

O trecho de código abaixo percorre arquivos de séries temporais em uma pasta, aplica o teste ADF e armazena os resultados:

```python
from statsmodels.tsa.stattools import adfuller
import pandas as pd
import os

# Caminho para os arquivos por estado
caminho = 'caminho_para_sua_pasta/Pernambuco'  # exemplo

# Lista para armazenar resultados
resultados_adf = []

# Iterar sobre os arquivos CSV da pasta
for arquivo in os.listdir(caminho):
    if arquivo.endswith('.csv'):
        df = pd.read_csv(os.path.join(caminho, arquivo))

        # Verifica se há uma coluna temporal e de dados
        if df.shape[1] >= 2:
            nome_serie = arquivo.split('.')[0]
            serie = df.iloc[:, 1].dropna()

            try:
                adf_result = adfuller(serie)

                resultados_adf.append({
                    'arquivo': nome_serie,
                    'ADF Statistic': adf_result[0],
                    'p-value': adf_result[1],
                    'lags used': adf_result[2],
                    'nobs': adf_result[3],
                    'critical value (1%)': adf_result[4]['1%'],
                    'critical value (5%)': adf_result[4]['5%'],
                    'critical value (10%)': adf_result[4]['10%'],
                    'conclusão': 'Estacionária' if adf_result[1] < 0.05 else 'Não estacionária'
                })
            except Exception as e:
                print(f"Erro ao processar {nome_serie}: {e}")

# Converter resultados para DataFrame
df_resultados_adf = pd.DataFrame(resultados_adf)
print(df_resultados_adf)



# Análise de Estacionariedade com Teste de Dickey-Fuller Aumentado (ADF)

Ao trabalhar com séries temporais, um passo essencial é verificar se a série é **estacionária**. Modelos como **ARIMA** exigem que a série seja estacionária — isto é, que suas propriedades estatísticas como **média**, **variância** e **autocorrelação** não mudem ao longo do tempo.

## 📌 Teste de Dickey-Fuller Aumentado (ADF)

O **ADF (Augmented Dickey-Fuller)** é um teste estatístico que verifica a presença de uma **raiz unitária**, ou seja, se a série é **não-estacionária**.

### 🧪 Hipóteses do Teste:

- **H₀ (nula):** A série é **não-estacionária** (possui raiz unitária).
- **H₁ (alternativa):** A série é **estacionária** (não possui raiz unitária).

### 📈 Interpretação do p-valor:

- Se **p-valor < 0.05** (nível de significância comum), **rejeitamos H₀** → A série é **estacionária**.
- Se **p-valor ≥ 0.05**, **falhamos em rejeitar H₀** → A série é **não-estacionária**.

---

## 📂 Aplicando o Teste ADF em Arquivos de Séries Temporais

O trecho de código abaixo percorre os arquivos de séries temporais, aplica o teste de Dickey-Fuller e armazena os resultados em um DataFrame.

```python
from statsmodels.tsa.stattools import adfuller
import pandas as pd
import os

# Caminho para os arquivos por estado
caminho = 'caminho_para_sua_pasta/Pernambuco'  # exemplo: pode ser alterado dinamicamente

# Lista para armazenar resultados
resultados_adf = []

# Iterar sobre os arquivos CSV da pasta
for arquivo in os.listdir(caminho):
    if arquivo.endswith('.csv'):
        df = pd.read_csv(os.path.join(caminho, arquivo))

        # Verifica se há uma coluna temporal e de dados
        if df.shape[1] >= 2:
            nome_serie = arquivo.split('.')[0]  # nome do arquivo sem extensão
            serie = df.iloc[:, 1].dropna()  # considera a segunda coluna como série

            try:
                adf_result = adfuller(serie)

                resultados_adf.append({
                    'arquivo': nome_serie,
                    'ADF Statistic': adf_result[0],
                    'p-value': adf_result[1],
                    'lags used': adf_result[2],
                    'nobs': adf_result[3],
                    'critical value (1%)': adf_result[4]['1%'],
                    'critical value (5%)': adf_result[4]['5%'],
                    'critical value (10%)': adf_result[4]['10%'],
                    'conclusão': 'Estacionária' if adf_result[1] < 0.05 else 'Não estacionária'
                })
            except Exception as e:
                print(f"Erro ao processar {nome_serie}: {e}")

# Converter resultados para DataFrame
df_resultados_adf = pd.DataFrame(resultados_adf)

# Exibir os resultados
print(df_resultados_adf)
---
O Teste ADF é uma ferramenta fundamental na análise de séries temporais. Ele permite identificar se transformações como diferenciação (differencing) são necessárias antes de aplicar modelos como ARIMA ou SARIMA. Uma vez identificada a presença de não estacionariedade, podemos aplicar transformações e reavaliar com o ADF até que a estacionariedade seja alcançada.

----
An LSTM is more or less an RNN that uses additional weights to determine when its storage cells are written to, read from, or erased. In an RNN the cells are simply written to and read from every time.

So you need to store those additional weights if you are using an LSTM, and you also need additional operations to compute how „open“ the cells are to being written and read. This „openness“ is also stored as a so-called cell state alongside the contents of the cell, meaning you need more storage there as well.

With how fast computers are, it usually doesn’t make a huge difference, but if you stack a lot of LSTMs or have really long sequences, like, thousands of elements, it adds up.

However, the additional logic also makes LSTMs more powerful and stable. So there are often situations where you would need several RNN layers to replace a single LSTM layer - in which case the LSTM is more efficient.

About sequence length, I usually start with a length of 20, so your 19 is already as close as it gets. You should look into whether increasing it further also further improves performance though.

Edit: I‘d say that typically, RNNs are stable enough to handle sequences of a few dozen to maybe around a hundred values. After that, you‘ll start to really see the benefits of LSTMs, which can process into the thousands of values. If you have a sequence length of, like, ten thousand values or beyond that, you should look into S5, H3 if what you’re doing needs associative recall of specific old sequence elements, or other sequence model architecture based on SSMs.
--- 
### 🔗 Referências
* [Pré-processamento de Séries Temporais - 365 Data Science](https://365datascience.com/tutorials/time-series-analysis-tutorials/pre-process-time-series-data/)
* [Preprocessing para aprendizado supervisionado - Towards Data Science](https://towardsdatascience.com/preprocessing-time-series-data-for-supervised-learning-2e27493f44ae)
* [Técnica de Data Windowing - LinkedIn](https://www.linkedin.com/pulse/data-windowing-technique-used-time-series-forecasting-alejandro/)
* [Rolling Windows - Medium](https://medium.com/@karamel.itu/time-series-rolling-windows-5cf9ec500e83)
* [EDA em Séries Temporais - Medium](https://medium.com/data-and-beyond/mastering-exploratory-data-analysis-eda-everything-you-need-to-know-7e3b48d63a95)

## 🔎 Artigos Científicos e Livros

### Livros Base
* *Análise de Séries Temporais* – Morettin & Toloi
* *Econometria Básica* – Damodar Gujarati
* *Elementos de Estatística Computacional* – Frery & Cribari Neto
* *Machine Learning* – Tom Mitchell  
    [PDF](https://www.cs.cmu.edu/~tom/files/MachineLearningTomMitchell.pdf)

### Artigos do Prof. Fausto
* [IEEExplore 2014 - Previsão com Híbrido PSO + SVM](https://ieeexplore.ieee.org/abstract/document/6974534)
* [Neurocomputing 2015 - Híbrido com Wavelet](https://www.sciencedirect.com/science/article/abs/pii/S0925231215016057)
* [Knowledge-Based Systems 2019 - ELM Otimizado](https://www.sciencedirect.com/science/article/abs/pii/S0950705119301327)
* [IEEE 2021 - Forecast com PSO + Deep](https://ieeexplore.ieee.org/abstract/document/9340584)

### Outros Artigos
* [Forecasting with artificial neural networks:The state of the art](https://www.oscogen.ethz.ch/members/literature_restricted%20access/ann_for_001.pdf)


## ⚙️ Modelos de Previsão

### 🔸 ARIMA e SARIMA
- [ARIMA do zero em Python - Medium](https://medium.com/analytics-vidhya/arima-model-from-scratch-in-python-489e961603ce)
- [Como o ARIMA funciona - Burak Ayy](https://burakayy.com/blog/how-arima-works)
- [Treinamento SARIMA passo a passo - MLPills](https://mlpills.dev/time-series/how-to-train-a-sarima-model-step-by-step/)
- [Comparação ARIMA, SARIMA, SARIMAX - Towards Data Science](https://towardsdatascience.com/time-series-forecasting-with-arima-sarima-and-sarimax-ee61099e78f6/)
- [Forecasting com SARIMA - Medium](https://medium.com/@ozdogar/time-series-forecasting-using-sarima-python-8db28f1d8cfc)
https://www.eng.uwaterloo.ca/~kwhipel/Time%20Series%20Book.htm
https://www.datacamp.com/tutorial/arima

https://medium.com/@learn-simplified/build-arima-model-from-scratch-part-1-b72b73ba230f

https://www.datacamp.com/tutorial/arima

https://www.kaggle.com/code/phunghieu/arima-from-scratch



\subsection{Classical Statistical methods:}
For univariate time series, methods such as interpolation and autoregressive models, such as ARIMA~\cite{bartholomew1971time} and SARIMA~\cite{hamzaccebi2008improving}), are often more useful. However, when dealing with the complexity of MTS, they may not fully capture the relationships between different variables in the dataset.
####o que e o modelo arima

 é um modelo estatístico amplamente utilizado para previsão de séries temporais.
 Ele combina três componentes principais:
AutoRegressivo (AR): A relação entre uma observação e um número de lags de si mesma.
Média Móvel (MA): A modelagem do erro como uma combinação linear de erros anteriores.
Integração (I): Diferenças sucessivas da série para torná-la estacionária.


O modelo ARIMA é um modelo autorregressivo integrado de médias móveis.



####o que é o sarima
Quando há sazonalidade nos dados, o modelo SARIMA (Seasonal ARIMA) é uma extensão do ARIMA, que incorpora componentes sazonais, combinando variações sazonais e não sazonais. Ele é conhecido como um modelo multiplicativo



### 🔸 SVM 
- é um algoritmo supervicionado de aprendizado de maquina que classifica os dados , usando 
 linha ideal ou a partir do  hiper plano , que é um conceito que generaliza a ideia de um plano no espaço tridimensional para espaços matemáticos de dimensões arbitrária,  (optimal line) qmaximiza a distancias entre as classes em um espaço N dimencional.

Os SVMs são comumente usados em problemas de classificação. Elas distinguem entre duas classes encontrando o hiperplano ideal que maximiza a margem entre os pontos de dados mais próximos de classes opostas. O número de recursos nos dados de entrada determina se o hiperplano é uma linha em um espaço bidimensional ou um plano em um espaço n-dimensional. Como vários hiperplanos podem ser encontrados para diferenciar as classes, a maximização da margem entre os pontos permite que o algoritmo encontre o melhor limite de decisão entre as classes. Isso, por sua vez, permite que ele generalize bem para novos dados e faça previsões de classificação precisas. As linhas adjacentes ao hiperplano ideal são conhecidas como vetores de suporte, pois esses vetores passam pelos pontos de dados que determinam a margem máxima.
o algoritmo svm é amplamente utilizado em aprendizado de maquina devido a sua qualidadade de linar com a tarefa de classificaçao lineares e nao lineares.
contudo quando os dados não estao linearmente separados , as funçoes de kernel sao usadas para transformar os dados higher-dimensional space to enable linear separation.
 This application of kernel functions can be known as the “kernel trick”, and the choice of kernel function, such as linear kernels, polynomial kernels, radial basis function (RBF) kernels, or sigmoid kernels, depends on data characteristics and the specific use case.

<img scr ="https://www.ibm.com/content/dam/connectedassets-adobe-cms/worldwide-content/creative-assets/s-migr/ul/g/8f/27/3-1_svm_optimal-hyperplane_max-margin_support-vectors-2-1.png">

linear svms sao usadas com  linearly separable data, o que significa que os dados nao precisam de nenhuma forma serem transformados para separar os dados de diferentes classes. 

### 🔸The decision boundary

### 🔸 LSTM e Deep Learning
- [LSTM com Tensorflow/Keras - Curiousily](https://curiousily.com/posts/time-series-forecasting-with-lstms-using-tensorflow-2-and-keras-in-python/)
- [LSTM para COVID-19 - Curiousily](https://curiousily.com/posts/time-series-forecasting-with-lstm-for-daily-coronavirus-cases/)
- [Previsão de Demanda com LSTM - Curiousily](https://curiousily.com/posts/demand-prediction-with-lstms-using-tensorflow-2-and-keras-in-python/)
- [LSTM no YouTube (tutorial)](https://www.youtube.com/watch?v=c0k-YLQGKjY&t=1379s)
- [Exemplo prático de LSTM no Kaggle](https://www.kaggle.com/code/paulorzp/laborat-rio-12b-usando-lstm-em-s-ries-temporais)
- [Vantagens e Desvantagens do LSTM - Medium](https://medium.com/@prudhviraju.srivatsavaya/lstm-implementation-advantages-and-diadvantages-914a96fa0acb)
- [Previsão de ações com LSTM - Medium](https://medium.com/datarisk-io/introdu%C3%A7%C3%A3o-%C3%A0s-redes-lstm-prevendo-valor-de-a%C3%A7%C3%B5es-na-bolsa-df270ca0cee5)

Com certeza! Vamos aprofundar a seção sobre LSTM e Deep Learning para previsão de séries temporais, tornando o conteúdo mais robusto e confiável.

### 🔸 LSTM e Deep Learning para Séries Temporais

Redes Neurais Recorrentes (RNNs) e, em particular, as Redes de Memória de Longo Prazo (LSTMs), representam uma classe poderosa de modelos de aprendizado profundo que se destacam no processamento e previsão de dados sequenciais, como séries temporais. Sua arquitetura intrínseca permite que capturem dependências temporais complexas, tornando-as adequadas para modelar padrões de longo prazo em dados que evoluem ao longo do tempo.

#### Redes Neurais Recorrentes (RNNs)

As RNNs são projetadas especificamente para lidar com sequências de dados. Diferentemente das redes neurais feedforward tradicionais, as RNNs incorporam mecanismos de *feedback* que permitem que informações de passos anteriores na sequência influenciem o processamento do passo atual. Essa capacidade de "memória" torna as RNNs teoricamente capazes de aprender dependências temporais.

A arquitetura básica de uma RNN envolve uma unidade recorrente que recebe a entrada atual e o estado oculto do passo anterior, produzindo um novo estado oculto e uma saída. Esse estado oculto atua como uma memória, carregando informações relevantes sobre a história da sequência.

No entanto, as RNNs tradicionais enfrentam desafios significativos ao aprender dependências de longo prazo devido ao problema do **vanishing gradient** (gradiente desaparecendo) e, em menor grau, ao **exploding gradient** (gradiente explodindo) durante o processo de treinamento com backpropagation através do tempo (BPTT).

#### Redes de Memória de Longo Prazo (LSTMs)

As LSTMs são uma arquitetura de RNN que foi explicitamente projetada para mitigar os problemas do vanishing e exploding gradients, permitindo que a rede aprenda dependências de longo prazo de forma mais eficaz. Elas introduzem uma unidade de memória mais complexa, chamada **célula de memória**, que é capaz de manter informações por longos períodos de tempo.

A célula de memória da LSTM é controlada por três mecanismos de *gating* (portões):

* **Portão de Entrada (Input Gate):** Controla quais novas informações devem ser armazenadas na célula de memória.
* **Portão de Esquecimento (Forget Gate):** Controla quais informações existentes na célula de memória devem ser descartadas.
* **Portão de Saída (Output Gate):** Controla quais informações da célula de memória devem ser usadas para gerar o estado oculto e a saída da LSTM.

Esses portões utilizam funções sigmóides para produzir valores entre 0 e 1, atuando como interruptores que modulam o fluxo de informações. A interação desses portões permite que a LSTM aprenda seletivamente a reter, atualizar e liberar informações ao longo da sequência temporal.

**Vantagens das LSTMs para Séries Temporais:**

* **Captura de Dependências de Longo Prazo:** A principal vantagem das LSTMs é sua capacidade de modelar relações temporais que se estendem por longas sequências, crucial para muitas tarefas de previsão de séries temporais.
* **Lidando com Dados Sequenciais Complexos:** As LSTMs podem aprender padrões complexos e não lineares em dados de séries temporais, incluindo sazonalidade, tendências e outros padrões intrincados.
* **Robustez a Ruído:** As células de memória e os mecanismos de gating tornam as LSTMs relativamente robustas a ruídos e irregularidades nos dados.
* **Flexibilidade na Arquitetura:** As LSTMs podem ser combinadas em arquiteturas profundas (múltiplas camadas LSTM) e integradas com outras camadas de redes neurais (como camadas densas) para modelar hierarquias de padrões nos dados.

**Desafios e Considerações ao Usar LSTMs:**

* **Complexidade Computacional:** O treinamento de modelos LSTM pode ser computacionalmente intensivo e demorado, especialmente para sequências longas e arquiteturas profundas.
* **Necessidade de Dados Significativos:** As LSTMs geralmente requerem uma quantidade considerável de dados de treinamento de alta qualidade para aprender representações eficazes.
* **Ajuste de Hiperparâmetros:** A arquitetura da rede LSTM (número de camadas, número de unidades por camada) e os hiperparâmetros de treinamento (taxa de aprendizado, batch size, número de épocas) precisam ser cuidadosamente ajustados para obter um bom desempenho.
* **Interpretabilidade:** Como outras redes neurais profundas, os modelos LSTM podem ser difíceis de interpretar, tornando a compreensão dos motivos por trás de suas previsões um desafio.
* **Pré-processamento de Dados:** O desempenho das LSTMs é altamente dependente do pré-processamento adequado dos dados de séries temporais, incluindo normalização, tratamento de valores faltantes e criação de sequências de entrada apropriadas (janelamento).

**Deep Learning para Séries Temporais:**

As LSTMs são apenas um componente do arsenal de modelos de aprendizado profundo para séries temporais. Outras arquiteturas e técnicas incluem:

* **RNNs com Mecanismos de Atenção:** Permitem que o modelo se concentre nas partes mais relevantes da sequência de entrada ao fazer previsões.
* **GRUs (Gated Recurrent Units):** Uma variante mais simplificada das LSTMs com menos parâmetros.
* **CNNs (Redes Neurais Convolucionais) 1D:** Podem ser usadas para extrair padrões locais ao longo da dimensão temporal da série.
* **Modelos Transformer:** Originalmente desenvolvidos para processamento de linguagem natural, os Transformers têm mostrado resultados promissores em tarefas de previsão de séries temporais, especialmente para dependências de longo alcance.
* **Modelos Híbridos:** A combinação de diferentes arquiteturas de deep learning (por exemplo, CNNs + LSTMs) ou a integração de modelos estatísticos tradicionais com redes neurais profundas (como mencionado na seção de modelos híbridos do seu projeto) pode levar a um melhor desempenho em certos cenários.

A escolha da arquitetura de deep learning mais adequada para uma tarefa de previsão de séries temporais específica depende das características dos dados (comprimento da sequência, sazonalidade, ruído), da complexidade dos padrões a serem modelados e dos recursos computacionais disponíveis.

**Confiabilidade das Fontes:**

As fontes listadas fornecem tutoriais práticos e exemplos de implementação de LSTMs usando bibliotecas populares como TensorFlow e Keras (Curiousily, Kaggle). Medium é uma plataforma de blogs onde autores compartilham suas experiências e conhecimentos, o que pode ser útil para entender conceitos e obter exemplos práticos, mas a confiabilidade pode variar dependendo do autor. O tutorial no YouTube também pode ser útil para uma introdução visual.

Para uma compreensão mais profunda e confiável dos fundamentos teóricos das LSTMs e do aprendizado profundo para séries temporais, é recomendado consultar livros acadêmicos, artigos de pesquisa revisados por pares e documentação oficial de bibliotecas de deep learning (TensorFlow, PyTorch).

Espero que esta expansão forneça uma compreensão mais completa e confiável do uso de LSTMs e deep learning para previsão de séries temporais!

#### Redes Neurais

**O que é uma rede neural artificial?**

Uma rede neural artificial é um modelo computacional inspirado na estrutura e no funcionamento do cérebro humano, particularmente na forma como os neurônios biológicos se comunicam. Essencialmente, são algoritmos de reconhecimento de padrões que identificam regularidades em dados de entrada e atribuem significado a esses padrões.

**Neurônios Artificiais e Conexões**

O bloco fundamental de uma rede neural artificial é o neurônio artificial, frequentemente modelado a partir do conceito de um perceptron. Um neurônio artificial recebe múltiplos sinais de entrada, cada um associado a um peso (representado por um vetor). Esses sinais ponderados são combinados através de um produto escalar, ao qual se adiciona um valor de bias (que não depende das entradas).

Em analogia com o neurônio biológico – uma célula que conduz sinais elétricos em uma única direção, composta por um corpo celular (onde reside o núcleo), um axônio (que transmite o sinal) e dendritos (que conectam o neurônio a outros) – o neurônio artificial opera de forma semelhante. Para que um neurônio biológico dispare um sinal, ele precisa receber um estímulo de entrada com uma intensidade mínima. Uma vez atingido esse limiar, um impulso elétrico se propaga ao longo do axônio, alcançando o corpo celular e, subsequentemente, outros neurônios.

De maneira análoga, o neurônio artificial recebe sinais que passam por uma função de ativação, gerando o sinal de saída do neurônio. Uma característica importante é que cada sinal de entrada pode ter uma relevância diferente para o neurônio, determinada pelo seu peso associado. Esse peso indica a contribuição de cada sinal para a ativação do neurônio.

As redes neurais se destacam por considerar as interações entre os seus elementos. Essa capacidade as torna particularmente eficazes no processamento de dados complexos como texto, vídeo e som. A arquitetura básica envolve nós de entrada que se conectam a nós em uma ou mais camadas escondidas, culminando em um nó de saída. A capacidade da rede de capturar interações complexas tende a aumentar com o número de nós presentes nas camadas escondidas. A conexão entre a camada de entrada e a camada escondida é caracterizada pelos pesos associados a cada ligação.

#### Redes Neurais Recorrentes (RNN)

As Redes Neurais Recorrentes (RNN) surgem como uma solução para o processamento de dados sequenciais, superando as limitações das redes neurais feedforward tradicionais ao introduzirem o conceito de loops. Esses loops permitem que a informação seja persistida ao longo da sequência.

**Funcionamento de uma RNN Padrão:**

Observe a seguinte representação visual do funcionamento de uma RNN padrão:

![RNN Padrão](https://miro.medium.com/v2/resize:fit:640/format:webp/0*6QxUX5KrH77f6Lm1.png)

As RNNs são comumente utilizadas para lidar com dados sequenciais e séries temporais. Podemos representar uma sequência de dados como $x = (x^{(1)}, x^{(2)}, ..., x^{(t)})$, onde $t$ representa o instante de tempo, variando de um momento inicial 1 até um tempo $t$ (conceitualmente, uma linha do tempo).

**Arquitetura da RNN:**

A arquitetura de uma RNN pode ser visualizada na seguinte imagem (a RNN é destacada na parte direita):

![Arquitetura RNN](https://miro.medium.com/v2/resize:fit:640/format:webp/1*JOkrQoJ3J3-451GzRcayRg.png)

Nessa representação, observamos um neurônio (denotado por $h$) que recebe $x^{(t)}$ como entrada no instante de tempo $t$. Por exemplo, $x^{(t)}$ poderia ser uma palavra em uma frase na posição $t$.

$h^{(t)}$ representa o estado escondido (*Hidden State*), um conceito que será detalhado posteriormente. O valor de $h^{(t)}$ é calculado com base na entrada atual ($x^{(t)}$) e no estado escondido do instante de tempo anterior ($h^{(t-1)}$), de acordo com a seguinte fórmula:

$$h^{(t)} = f(U x^{(t)} + W h^{(t-1)})$$

onde $f$ é uma função de transformação não linear, como a tangente hiperbólica (tanh) ou a função ReLU.

A RNN possui conexões de entrada para a camada escondida parametrizadas por uma matriz de pesos $U$, conexões recorrentes entre as unidades escondidas parametrizadas por uma matriz de pesos $W$, e conexões da camada escondida para a saída parametrizadas por uma matriz de pesos $V$. Um aspecto fundamental das RNNs é que todos esses pesos ($U$, $V$, e $W$) são compartilhados ao longo do tempo.
Com certeza! Aqui está o texto formatado em Markdown, organizado e com melhor coesão:

```markdown
### Neurônio Artificial e Função de Ativação

A operação fundamental de um neurônio artificial envolve uma **função linear**, que pode ser expressa como:

$$(x_i \cdot W_{ij}) + bias$$

onde $x_i$ representa as entradas, $W_{ij}$ são os pesos associados a essas entradas, e o *bias* é um termo constante.

O resultado dessa função linear é então passado para uma **função de ativação**. O papel crucial da função de ativação é determinar quais sinais serão considerados relevantes e propagados para a próxima camada da rede neural. Ela introduz não-linearidade ao modelo, permitindo que a rede aprenda relações complexas nos dados.

Uma função de ativação amplamente utilizada é a **ReLU (Rectified Linear Unit)**. Sua definição matemática é simples:

$$ReLU(x) = \begin{cases} x, & \text{se } x > 0 \\ 0, & \text{se } x \le 0 \end{cases}$$

Isso significa que a saída da ReLU é o próprio valor de entrada se ele for positivo, e zero caso contrário.

É importante notar que o **tamanho do vetor de pesos** em um neurônio artificial é sempre igual ao tamanho do vetor de entrada. Isso garante que cada entrada tenha um peso correspondente que determine sua influência na saída do neurônio.

Em essência, uma **rede neural** pode ser vista como um **grafo computacional**, onde os nós representam as operações (neurônios e funções de ativação) e as arestas representam o fluxo de dados.

A operação $(x_i \cdot W_{ij}) + bias$ é um exemplo de uma **combinação afim**.

### Preparação de Dados com PyTorch

O código a seguir demonstra como criar um conjunto de dados algébrico personalizado e carregadores de dados utilizando a biblioteca PyTorch:

```python
import torch
from torch.utils.data import Dataset, DataLoader
import numpy.random as urand

class AlgebraicDataset(Dataset):
    """
    Cria um conjunto de dados de pares ordenados (x, f(x)).
    """
    def __init__(self, f, interval, nsamples):
        """
        Args:
            f (callable): A função a ser aplicada aos valores de x.
            interval (list): O intervalo [inicio, fim] de onde os valores de x serão amostrados.
            nsamples (int): O número de amostras a serem geradas.
        """
        x = urand.uniform(interval[0], interval[1], nsamples)
        self.data = [(xi, f(xi)) for xi in x]

    def __len__(self):
        """
        Retorna o número total de amostras no dataset.
        """
        return len(self.data)

    def __getitem__(self, idx):
        """
        Retorna o item (x, f(x)) no índice especificado.
        """
        return self.data[idx]

# Definição da função linear, intervalo e número de amostras
line = lambda x: 2 * x + 3
interval = [-10, 10]
train_nsamples = 1000
test_nsamples = 100

# Criação dos datasets de treinamento e teste
train_dataset = AlgebraicDataset(line, interval, train_nsamples)
test_dataset = AlgebraicDataset(line, interval, test_nsamples)

# Criação dos DataLoaders para iteração eficiente sobre os datasets
train_dataloader = DataLoader(train_dataset, batch_size=train_nsamples, shuffle=True)
test_dataloader = DataLoader(test_dataset, batch_size=test_nsamples, shuffle=True)

# Verificação do dispositivo de treinamento (GPU se disponível, CPU caso contrário)
device = "cuda" if torch.cuda.is_available() else "cpu"
print(f"Rodando na {device}")

# Supondo que LineNetwork() seja uma classe de modelo definida em outro lugar
# model = LineNetwork().to(device)
```

O `AlgebraicDataset` personalizado gera pares ordenados $(x, f(x))$ dentro de um intervalo especificado. O `DataLoader` do PyTorch facilita a leitura dos dados em batches, o que é crucial para o treinamento eficiente de redes neurais. O parâmetro `shuffle=True` garante que os dados sejam embaralhados em cada época de treinamento, ajudando a evitar que o modelo aprenda a ordem dos dados.

### Treinamento de Redes Neurais

O treinamento de uma rede neural envolve ajustar seus **parâmetros** (pesos e biases) para que o modelo possa mapear as entradas para as saídas desejadas com a maior precisão possível. A rede é um **modelo paramétrico de uma função**, e esses parâmetros são refinados durante o processo de aprendizagem.

Para que o aprendizado ocorra, a rede precisa de **feedback** para avaliar seu desempenho e ajustar seus parâmetros na direção correta. Isso é feito através da **função de perda** (*loss function*), que quantifica o erro entre as previsões do modelo e os valores reais. A função de perda é uma métrica que indica o quão perto ou quão longe as previsões estão da verdade.

Um exemplo comum de função de perda é o **erro quadrático médio (MSE - Mean Squared Error)**, calculado pela média da soma dos quadrados das diferenças entre as previsões e os valores reais. A raiz quadrada do MSE é o **RMSE (Root Mean Squared Error)**.

```python
import torch.nn as nn
import torch.optim as optim

# Função de perda: Erro Quadrático Médio
lossfunc = nn.MSELoss()

# Otimizador: Gradiente Descendente Estocástico (SGD)
# optimizer = optim.SGD(model.parameters(), lr=learning_rate)
```

Para minimizar a função de perda e melhorar o desempenho do modelo, utilizamos algoritmos de otimização, como o **Gradiente Descendente**. O Gradiente Descendente é um método iterativo que ajusta os parâmetros do modelo na direção do negativo do gradiente da função de perda em relação a esses parâmetros.

A versão **Estocástica (SGD)** do Gradiente Descendente calcula o gradiente usando apenas um subconjunto aleatório dos dados (um batch) em cada iteração. Essa abordagem introduz aleatoriedade, o que pode ajudar a escapar de mínimos locais na função de perda. A consequência de usar apenas partes dos dados em cada atualização é o que torna o método estocástico.

É importante notar que o Gradiente Descendente em sua forma básica pode não identificar se o modelo atingiu um mínimo global na função de perda.

O **tamanho do passo** dado na direção do gradiente é controlado pela **taxa de aprendizado (*learning rate* - `lr`)**, um hiperparâmetro crucial que precisa ser ajustado cuidadosamente.

```python
def test(model, dataloader, lossfunc):
    """
    Avalia o desempenho do modelo no conjunto de dados fornecido.
    """
    model.eval()  # Coloca o modelo em modo de avaliação
    cumloss = 0.0
    with torch.no_grad():  # Desativa o cálculo de gradientes durante a avaliação
        for X, y in dataloader:
            X = X.unsqueeze(1).float().to(device)
            y = y.unsqueeze(1).float().to(device)
            pred = model(X)
            loss = lossfunc(pred, y)
            cumloss += loss.item()
    return cumloss / len(dataloader)

# O tamanho do passo (learning rate) do gradiente descendente pode ser modificado
```

### Otimização e Conceitos Avançados

Além do Gradiente Descendente, existem outros **algoritmos de otimização**, como algoritmos genéticos e otimização por enxame de partículas (PSO), que podem ser usados para treinar redes neurais e otimizar seus **hiperparâmetros** (parâmetros que não são aprendidos durante o treinamento, como a taxa de aprendizado e a arquitetura da rede).

Outras técnicas e conceitos importantes incluem:

* **Implementação manual de embaralhamento (shuffle) em Python:** Permite um controle mais granular sobre o processo de aleatorização dos dados.
* **Implementação manual de Min-Max Scaling em Python:** Uma técnica de normalização que escala os dados para um intervalo específico (geralmente \[0, 1\] ou \[-1, 1\]). É importante calcular os valores mínimo e máximo apenas no conjunto de treinamento para evitar o vazamento de informações do conjunto de teste.
* **ELM (Extreme Learning Machine):** Uma arquitetura de rede neural com camadas ocultas de ativação aleatória e pesos de saída determinados analiticamente.
* **Álgebra Matricial e Implementação:** A compreensão da álgebra matricial é fundamental para implementar e otimizar operações em redes neurais.
* **Processo de Desnormalização:** A reversão de técnicas de normalização para interpretar as previsões do modelo na escala original dos dados.

### Conceitos Básicos de Processos Estocásticos e Séries Temporais

* **Processos Estocásticos e Séries Temporais:** Um processo estocástico é uma sequência de variáveis aleatórias indexadas por tempo ou espaço. Uma série temporal é uma sequência de dados coletados em pontos de tempo sucessivos.
* **Estacionariedade:** Uma propriedade de um processo estocástico onde suas propriedades estatísticas (média, variância, autocovariância) não mudam ao longo do tempo.
* **Função de Autocovariância e Espectro:** A função de autocovariância mede a correlação entre os valores de um processo em diferentes pontos no tempo. O espectro (ou densidade espectral de potência) descreve a distribuição da potência do sinal em diferentes frequências.

### Processos ARMA Estacionários

* **Modelos Autoregressivos (AR):** Modelos que preveem o valor atual de uma série temporal com base em seus valores passados.
* **Modelos de Médias Móveis (MA):** Modelos que preveem o valor atual com base em erros de previsão passados.
* **Modelos ARMA (Autoregressive Moving Average):** Combinam componentes autoregressivos e de médias móveis.
* **Modelos ARIMA (Autoregressive Integrated Moving Average):** Estendem os modelos ARMA para lidar com séries temporais não estacionárias através da diferenciação.
* **Modelo Linear Geral e Modelos Harmônicos:** Outras abordagens para modelar séries temporais.

### Análise Espectral

* **Séries de Fourier:** Uma representação de uma função periódica como uma soma de senos e cossenos.
* **Análise de Funções Periódicas e Não Periódicas:** A análise de Fourier pode ser estendida para funções não periódicas através da Transformada de Fourier.
* **Representação Espectral de Processos Estacionários:** O espectro de um processo estacionário fornece informações sobre suas componentes de frequência.
* **Espectro Misto e Filtros Lineares:** Processos podem ter um espectro com componentes discretas e contínuas. Filtros lineares podem ser aplicados para modificar o espectro de um sinal.

### Estimação no Domínio do Tempo

* **Estimação da Média e da Função de Autocovariância:** Métodos para estimar essas propriedades estatísticas a partir de dados de séries temporais.
* **Identificação, Estimação e Previsão de Parâmetros de Modelos ARIMA:** Técnicas para determinar a ordem de um modelo ARIMA e estimar seus parâmetros, bem como usar o modelo para fazer previsões futuras.

### Estimação no Domínio da Frequência

* **A Transformada de Fourier Finita e o Periodograma:** Ferramentas para estimar o espectro de uma série temporal finita.
* **Estimadores Suavizados:** Métodos para reduzir a variância nas estimativas espectrais obtidas do periodograma.
```
---
Divisão dos Dados (Train/Test/Validation Split): Separar os dados históricos em conjuntos para treinamento do modelo, teste e, possivelmente, validação. É crucial que essa divisão respeite a ordem temporal, ou seja, os dados de teste devem ser posteriores aos dados de treino

Estatísticas de Janela (Rolling/Expanding Window Statistics): Cálculos como média móvel, desvio padrão móvel, etc., sobre períodos recentes

Lags da própria série: Valores passados da série que servem como preditores. A análise de ACF/PACF pode ajudar a identificar lags relevantes

Seleção e Definição do(s) Modelo(s): Escolher o(s) algoritmo(s) de previsão a serem utilizados, como ARIMA, modelos de Suavização Exponencial (como Holt-Winters), modelos de Machine Learning (como Regressão Linear, Random Forest, SVM) ou Redes Neurais (como LSTMs), ou uma combinação/abordagem híbrida

Treinamento do(s) Modelo(s): Ajustar o(s) modelo(s) selecionado(s) aos dados de treinamento. Isso pode envolver a otimização de hiperparâmetros

Treinamento do(s) Modelo(s): Ajustar o(s) modelo(s) selecionado(s) aos dados de treinamento. Isso pode envolver a otimização de hiperparâmetros

Previsão (Forecasting): Utilizar o(s) modelo(s) treinado(s) para gerar previsões para períodos futuros (no conjunto de teste ou validação)

Desnormalização / Back-transformation (se aplicável): Se a normalização (como MinMax) foi aplicada às variáveis de entrada do modelo e/ou se a previsão de um componente (como o resíduo) foi feita em escala normalizada, a previsão gerada pelo modelo deve ser DESNORMALIZADA (transformada de volta) para a escala original da série temporal. Este passo é fundamental para que a previsão final tenha a magnitude e unidades corretas [Como discutimos anteriormente; 470 menciona o processo de desnormalização].

Combinação / Recomposição (se aplicável): Em abordagens que envolvem a decomposição da série ou o uso de múltiplos modelos para prever diferentes componentes (por exemplo, prever a sazonalidade separadamente ou modelar os resíduos de um primeiro modelo com um segundo modelo), as previsões dos componentes individuais (após a desnormalização, se necessário) precisam ser combinadas para gerar a previsão final da série original [Como discutimos anteriormente; 140 descreve a combinação de previsões da componente sazonal e da série ajustada; 461 menciona combinação de modelos].

Avaliação do Desempenho: Comparar as previsões finais (agora na escala original) com os valores reais no conjunto de teste/validação usando métricas de avaliação apropriadas (como RMSE, MAE, MAPE, etc.)

Validação dos Resíduos do Modelo Final: Após o modelo ser ajustado e as previsões geradas, é importante analisar os resíduos (a diferença entre os valores reais e as previsões no conjunto de treino/validação) para garantir que eles se assemelham a um ruído branco (ou seja, não há mais padrões temporais não explicados pelo modelo)
---
# 📚 Repositório de Links e Materiais

## 🎓 Aulas e Google Classroom

- [Google Classroom - Aula](https://classroom.google.com/c/NzQ4MzgyNzkxOTgz/m/Njk5MzYzNzY5OTEx/details)
- [YouTube - Aula LSTM Parte 1](https://www.youtube.com/watch?v=FbxTVRfQFuI&list=PLEiEAq2VkUUIYQ-mMRAGilfOKyWKpHSip&index=4)
- [YouTube - Aula LSTM Parte 2](https://www.youtube.com/watch?v=lWkFhVq9-nc&t=214s)

## 💻 Google Colab e Notebooks

- [Colab - Exercícios de LSTM](https://colab.research.google.com/drive/1Vs0Po5UXSaaGwQ7aFXIXmzJlO2ltv9RV?usp=sharing&authuser=0)

## 🧠 Redes Neurais Recorrentes (RNN, LSTM, GRU)

- [Kaggle - RNN Tutorial por kcsener](https://www.kaggle.com/code/kcsener/8-recurrent-neural-network-rnn-tutorial)
- [Kaggle - LSTM e GRU Tutorial por thebrownviking20](https://www.kaggle.com/code/thebrownviking20/intro-to-recurrent-neural-networks-lstm-gru)
- [Kaggle - Decomposição de Séries Temporais](https://www.kaggle.com/code/chanakyavivekkapoor/decomposing-time-series-data)

## 📁 GitHub e Artigos Técnicos

- [GitHub - BRITS](https://github.com/caow13/BRITS)
- [NeurIPS Paper 2018 - BRITS](https://papers.nips.cc/paper_files/paper/2018/file/734e6bfcd358e25ac1db0a4241b95651-Paper.pdf)
- [PapersWithCode - BRITS](https://paperswithcode.com/paper/brits-bidirectional-recurrent-imputation-for)

---

## 🔸 Hybrid Mode (Modelos Híbridos)

- [Medium - Classificadores Híbridos em Séries Temporais](https://medium.com/@preeti.rana.ai/hybrid-classifiers-time-series-forecasting-88594988cc44)
- [Medium - Prophet + LSTM](https://subashpalvel.medium.com/time-series-forecasting-with-prophet-and-lstm-hybrid-mode-75f5295605e5)
- [YouTube - Tutorial Híbrido LSTM + Prophet](https://www.youtube.com/watch?v=E2_IhBKxBxM)

---

## 🤖 Otimização de Modelos

### ⚙️ Algoritmos Evolutivos (PSO)

- [PSO explicação simples com Python - Nathan.fun](https://nathan.fun/posts/2016-08-17/simple-particle-swarm-optimization-with-python/)
- [PSO em Python - GeeksforGeeks](https://www.geeksforgeeks.org/implementation-of-particle-swarm-optimization/)
- [PSO explicação prática - Medium](https://medium.com/data-science/what-the-hell-is-particle-swarm-optimization-pso-simplest-explanation-in-python-be296fc3b1ab)
- [PSO código e visualização - Towards Data Science](https://towardsdatascience.com/swarm-intelligence-coding-and-visualising-particle-swarm-optimisation-in-python-253e1bd00772/)
- [PSO implementado em Python - Medium](https://induraj2020.medium.com/implementing-particle-swarm-optimization-in-python-c59278bc5846)

---

## 🔎 Artigos Científicos e Livros

### 📘 Livros Base

- *Análise de Séries Temporais* – Morettin & Toloi  
- *Econometria Básica* – Damodar Gujarati  
- *Elementos de Estatística Computacional* – Frery & Cribari Neto  
- *Machine Learning* – Tom Mitchell ([PDF](https://www.cs.cmu.edu/~tom/files/MachineLearningTomMitchell.pdf))

### 📄 Artigos do Prof. Fausto

- [IEEExplore 2014 - Previsão com Híbrido PSO + SVM](https://ieeexplore.ieee.org/abstract/document/6974534)
- [Neurocomputing 2015 - Híbrido com Wavelet](https://www.sciencedirect.com/science/article/abs/pii/S0925231215016057)
- [Knowledge-Based Systems 2019 - ELM Otimizado](https://www.sciencedirect.com/science/article/abs/pii/S0950705119301327)
- [IEEE 2021 - Forecast com PSO + Deep Learning](https://ieeexplore.ieee.org/abstract/document/9340584)

### 📑 Outros Artigos

- [Forecasting with artificial neural networks: The state of the art (OSC Open)](https://www.oscogen.ethz.ch/members/literature_restricted%20access/ann_for_001.pdf)

---

## 🔬 Análise e Detecção de Anomalias em Séries Temporais

- [arXiv - Deep Learning for Time Series Anomaly Detection: A Survey](https://arxiv.org/abs/1905.13628)
- [ScienceDirect - Anomaly detection in time series](https://www.sciencedirect.com/science/article/pii/S0378437121004076)
- [IEEE - Review on Outlier/Anomaly Detection](https://ieeexplore.ieee.org/document/4626688)
- [ACM - DL for Anomaly Detection in Time-Series](https://dl.acm.org/doi/full/10.1145/3691338)
- [ACM - Microsoft Time-Series Anomaly Detection Service](https://dl.acm.org/doi/abs/10.14778/3538598.3538602)
- [ACM - Anomaly Detection on Time Series](https://dl.acm.org/doi/abs/10.1145/3292500.3330680)
- [IEEE - CNN + Transfer Learning for Time Series Anomaly Detection](https://ieeexplore.ieee.org/abstract/document/8926446)

---

## 🧠 Previsão Híbrida e Otimização

- [Hybrid Time Series Forecasting Methods for Travel Time Prediction (ScienceDirect)](https://www.sciencedirect.com/science/article/pii/S111001682100613X)
- [Understanding Memetic Algorithms (IndiaAI)](https://indiaai.gov.in/article/understanding-memetic-algorithm)
- [Computationally Efficient Hybrid ARIMA-SVR Model (IEEE)](https://ieeexplore.ieee.org/abstract/document/9523565)
- [Memetic Algorithm for Pattern Recognition (CBRN)](https://sbic.org.br/eventos/cbrn_2007/50100078-2/)

---

## 🧮 Modelos ARIMA e SARIMA

- [ARIMA do zero em Python - Medium](https://medium.com/analytics-vidhya/arima-model-from-scratch-in-python-489e961603ce)
- [Como o ARIMA funciona - Burak Ayy](https://burakayy.com/blog/how-arima-works)
- [Treinamento SARIMA passo a passo - MLPills](https://mlpills.dev/time-series/how-to-train-a-sarima-model-step-by-step/)
- [Comparação ARIMA, SARIMA, SARIMAX - Towards Data Science](https://towardsdatascience.com/time-series-forecasting-with-arima-sarima-and-sarimax-ee61099e78f6/)
- [Forecasting com SARIMA - Medium](https://medium.com/@ozdogar/time-series-forecasting-using-sarima-python-8db28f1d8cfc)
- [Estimando coeficientes ARIMA/SARIMA com GA - Medium](https://medium.com/@mouse3mic3/estimating-arima-and-sarima-coefficients-using-genetic-algorithm-03f24ab66589)
- [ARIMA from scratch part 1 - Medium](https://medium.com/@learn-simplified/build-arima-model-from-scratch-part-1-b72b73ba230f)
- [ARIMA Tutorial - Datacamp](https://www.datacamp.com/tutorial/arima)
- [ARIMA from scratch - Kaggle](https://www.kaggle.com/code/phunghieu/arima-from-scratch)

---

## 🔁 RNN, LSTM e Séries Temporais com Deep Learning

- [LSTM com Tensorflow/Keras - Curiousily](https://curiousily.com/posts/time-series-forecasting-with-lstms-using-tensorflow-2-and-keras-in-python/)
- [LSTM para COVID-19 - Curiousily](https://curiousily.com/posts/time-series-forecasting-with-lstm-for-daily-coronavirus-cases/)
- [Previsão de Demanda com LSTM - Curiousily](https://curiousily.com/posts/demand-prediction-with-lstms-using-tensorflow-2-and-keras-in-python/)
- [LSTM no YouTube (tutorial)](https://www.youtube.com/watch?v=c0k-YLQGKjY&t=1379s)
- [Kaggle - LSTM em Séries Temporais (Laboratório)](https://www.kaggle.com/code/paulorzp/laborat-rio-12b-usando-lstm-em-s-ries-temporais)
- [Vantagens e Desvantagens do LSTM - Medium](https://medium.com/@prudhviraju.srivatsavaya/lstm-implementation-advantages-and-diadvantages)
