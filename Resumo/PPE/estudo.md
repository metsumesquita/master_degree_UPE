
#Probabilidade e processos estocásticos

## Noções de Estatística

### Estatística Descritiva
A estatística descritiva tem como objetivo **descrever fatos** relacionados a um grupo, população ou amostra, sem tirar conclusões de caráter genérico. É um conjunto de técnicas destinadas à síntese de dados numéricos a partir de informações coletadas.

- **Não testamos hipóteses**.
- **Não fazemos testes**.

---

### Conceitos Primitivos

#### População
Conjunto universo de todos os elementos (pessoas, objetos, etc.) com uma característica comum, que é o objeto de estudo.

- **Parâmetro**: Medida numérica que descreve uma característica da população.
  - Média populacional: **μ**
  - Variância populacional: **σ²**
  - Desvio padrão populacional: **σ**

#### Amostra
Subconjunto não vazio de uma população.

- **Estatística**: Medida calculada a partir da amostra.
  - Média amostral: **x̄**
  - Variância amostral: **s²**
  - Desvio padrão amostral: **s**

---

### Censo vs. Estimação

#### Censo
- **Definição**: Avaliação direta de um parâmetro, obtida de todos os componentes da população.
- **Características**:
  - Caro.
  - Lento.
  - Quase sempre desatualizado.
  - **Não tem erro**.

#### Estimação
- **Definição**: Avaliação indireta de um parâmetro, com base em uma amostra.
- **Características**:
  - Mais comum.
  - Barato.
  - Rápido.
  - Atualizado.
  - Admite erro processual.
  - Confiabilidade menor que 100%.

---

### Dados Estatísticos

#### Dados Brutos
Dados obtidos diretamente da observação, sem organização numérica.

**Exemplo**:
```
Filhotes: {4, 2, 1, 3, 1, 2, 5, 6, 7}
```

#### Rol
Dados brutos organizados em ordem crescente ou decrescente.

**Exemplo**:
```
Filhotes: {1, 1, 2, 2, 3, 4, 5, 6, 7}
```

---

### Tipos de Dados

#### Dados Quantitativos
Possuem características numéricas.

1. **Discretos**: Assumem valores inteiros.
   - Exemplo: Número de alunos em uma sala (15 ou 16, mas não 15,5).
2. **Contínuos**: Assumem qualquer valor em um intervalo.
   - Exemplo: Altura (1,55 m), peso (55,5 kg).

#### Dados Qualitativos
Não possuem características numéricas.

1. **Nominais**: são dados categoricos, possuem caracteristica nao numerica,A ordem não importa.
   - Exemplo: Cor dos olhos, tipo sanguíneo.
2. **Ordinais**: são dados estatisticos,A ordem é relevante.
   - Exemplo: Classificação (baixo, médio, alto), nível de satisfação.

Aqui está o conteúdo que você forneceu sobre **Dados Contínuos**, organizado em **Markdown** para facilitar a visualização e o estudo:

---

### Dados Contínuos

#### Definição
Dados contínuos são aqueles que podem assumir **qualquer valor dentro de um intervalo de valores**. Eles são representados por números reais e podem ser fragmentados em decimais.

#### Exemplos
- **Altura**: 1,75 m, 1,80 m, etc.
- **Peso**: 70,5 kg, 89,3 kg, etc.
- **Salário**: R$ 2.500,50, R$ 3.000,75, etc.
- **Temperatura**: 23,5°C, 24,1°C, etc.

#### Explicação
Imagine dois bois, um pesando **70 kg** e outro pesando **89 kg**. Entre esses dois valores, é possível haver um número como **75,5 kg** ou **80,3 kg**. Isso ocorre porque os dados contínuos podem ser fragmentados em decimais, permitindo uma variação infinita dentro de um intervalo.

---

### Exercício de Fixação

#### Questão 1
Classifique as variáveis abaixo:

1. Tamanho de um objeto (grande, pequeno, médio): **Qualitativo Ordinal**.
2. Volume de água em um rio: **Quantitativo Contínuo**.
3. Número de clientes em uma fila: **Quantitativo Discreto**.
4. Número da seção de votação: **Qualitativo Nominal**.
5. Comprimento de um inseto: **Quantitativo Contínuo**.
6. Classe social: **Qualitativo Nominal**.

#### Questão 2
Classifique as variáveis:

1. Faixa etária de um indivíduo: **Qualitativo Ordinal**.
2. Número de pessoas que dão entrada em um hospital por hora: **Quantitativo Discreto**.

#### Questão 3
Sobre estatística aplicada, assinale a alternativa correta:

- **e) Censo é o processo utilizado para se medir as características de todos os membros de uma dada população**.

#### Questão 4
Assinale a alternativa que representa o conceito de variável quantitativa discreta:

- **a) É aquela que expressa o valor de uma contagem, por exemplo, idade, quantidade de TVs em uma casa, quantidade de habitantes em uma cidade**.

---

### Distribuição de Frequência

#### Definição
Representação tabular dos dados estatísticos, discretos ou contínuos, que resume grandes conjuntos de dados.

#### Tipos de Frequência

1. **Frequência Absoluta (Fa)**:
   - Número de vezes que um valor aparece.
2. **Frequência Relativa (Fr)**:
   - Razão entre a frequência absoluta e o número total de elementos.
   - Fórmula:  
     \[
     Fr = \frac{Fa}{n}
     \]
   - Para obter a porcentagem, multiplique por 100.
3. **Frequência Acumulada (Fac)**:
   - Somatório das frequências simples de uma variável com as frequências simples dos elementos que a antecedem.

**Exemplo**:
- 1 aluno assiste 4 disciplinas: **Fac = 1**.
- 6 alunos assistem 5 disciplinas: **Fac = 7 (6 + 1)**.
- 5 alunos assistem 6 disciplinas: **Fac = 12 (5 + 6 + 1)**.

---

## Referências
- [Aula 2 - Estatística](https://www.grancursosonline.com.br/aluno/curso/video/codigo/V3GmhgEULTQ%3D/v/cEfwjYiH3Rk%3D/c/E%2BeQFt%2Fioic%3D)

---

## Exercícios de Fixação - Aula 2: Noções de Probabilidade e Estatística

### Banca UFU-MG
Considere as seguintes variáveis:

- **A**: Tamanho do objeto (pequeno, médio, grande) → **Qualitativo Ordinal**.
- **B**: Volume de água em um rio → **Quantitativo Contínuo**.
- **C**: Número de clientes em uma fila → **Quantitativo Discreto**.
- **D**: Número da seção de votação → **Qualitativo Nominal**.
- **E**: Comprimento de um inseto → **Quantitativo Contínuo**.
- **F**: Classe social → **Qualitativo Ordinal**.

Com relação à classificação dos dados requeridos como variáveis de pesquisa, é correto afirmar que:

- **A**: As variáveis A, D, F são qualitativas. **(Certa)**
- **B**: As variáveis C e E são quantitativas contínuas. **(Errada)**
- **C**: As variáveis B e C são quantitativas discretas. **(Errada)**
- **D**: A variável D é qualitativa ordinal. **(Errada)**

---

### Banca NUCEPE
Com relação às classificações de tipos de variáveis, considere as variáveis:

1. **Faixa etária de um indivíduo** → **Qualitativa Ordinal**.
2. **Número de pessoas que dão entrada em um hospital por hora** → **Quantitativa Discreta**.

Essas duas variáveis podem ser classificadas, respectivamente, como:

- **A**: Qualitativa ordinal e qualitativa nominal. **(Errada)**
- **B**: Quantitativa discreta e qualitativa nominal. **(Errada)**
- **C**: Quantitativa discreta e qualitativa ordinal. **(Errada)**
- **D**: Ambas quantitativas discretas. **(Errada)**
- **E**: Qualitativa ordinal e quantitativa discreta. **(Certa)**

---
Aqui está o conteúdo que você forneceu sobre **Exercícios de Fixação** e **Revisão**, organizado e formatado em **Markdown** para facilitar a visualização e o estudo:

---

## Exercícios de Fixação - Estatística Aplicada

### Questão
Sobre estatística aplicada, é correto o que se afirma em?

- **a**: Parâmetros são medidas características de grupos, determinadas por meio de uma amostra aleatória.  
  **Errado**: Parâmetros estão diretamente ligados à **população**, não à amostra.

- **b**: A estatística descritiva é uma técnica pela qual são coletados dados de uma amostra, a partir do que são tomadas decisões sobre uma determinada população.  
  **Errado**: A estatística descritiva **não toma decisões**; ela apenas descreve os dados.

- **c**: A caracterização de uma população se dá por meio da observação de todos os componentes que a integram.  
  **Errado**: A caracterização de uma população pode ser feita por meio de uma **amostra**, não necessariamente de todos os componentes.

- **d**: A estatística inferencial compreende um conjunto de técnicas destinadas à síntese de dados numéricos.  
  **Errado**: A estatística inferencial **toma decisões** com base nos dados, não apenas sintetiza.

- **e**: Censo é um processo utilizado para se medir as características de todos os membros de uma determinada população.  
  **Certo**: O censo avalia **todos os membros** da população.

---

### Revisão do Exercício

#### Parâmetros e Estatísticas
- **a**: Os parâmetros são medidas características de grupos, determinadas por meio de uma **população**.  
  **Correto**: Parâmetros estão associados à população.

- **b**: A estatística inferencial é uma técnica que coleta dados de uma **amostra**, a partir do que são tomadas decisões sobre uma determinada população.  
  **Correto**: A estatística inferencial usa amostras para inferir sobre a população.

- **c**: A caracterização de uma população se dá por meio da observação de **parte** dos componentes que a integram.  
  **Correto**: A caracterização pode ser feita por meio de uma **amostra**.

- **d**: A estatística descritiva compreende um conjunto de técnicas destinadas à síntese de dados numéricos.  
 
---

### Resumo
| Afirmação | Correção | Explicação |
|-----------|----------|------------|
| **a** | Errado | Parâmetros estão ligados à população, não à amostra. |
| **b** | Errado | A estatística descritiva não toma decisões. |
| **c** | Errado | A caracterização pode ser feita por amostra. |
| **d** | Errado | A estatística inferencial toma decisões, não apenas sintetiza. |
| **e** | Certo | O censo avalia todos os membros da população. |

---



Aqui está o conteúdo que você forneceu sobre o **Exercício** e a **Revisão**, organizado e formatado em **Markdown** para facilitar a visualização e o estudo:

---

## Exercício: Variável Quantitativa Discreta

Assinale a alternativa que apresenta o conceito de **variável quantitativa discreta**:

- **A**: É aquela que expressa o valor de uma quantidade, por exemplo, idade, quantidade de habitantes de uma cidade, quantidade de televisões numa casa.  
  **Resposta certa**: Essa alternativa descreve corretamente uma variável quantitativa discreta, pois envolve contagens (números inteiros).

- **B**: É aquela que separa os indivíduos em classes com uma determinada ordem, por exemplo, nível de escolaridade (fundamental, médio, superior).  
  **Errado**: Isso descreve uma **variável qualitativa ordinal**.

- **C**: É aquela que expressa uma medida como um valor real, por exemplo, peso e altura.  
  **Errado**: Isso descreve uma **variável quantitativa contínua**.

- **D**: É aquela que separa os indivíduos em classes, mas não é possível estabelecer uma ordem, por exemplo, gênero, esporte praticado (futebol, basquete, ciclismo).  
  **Errado**: Isso descreve uma **variável qualitativa nominal**.

---

## Revisão do Exercício

### Tipos de Variáveis

1. **Variável Quantitativa Discreta**:
   - **Definição**: Expressa valores de contagem (números inteiros).
   - **Exemplos**: Idade, número de habitantes, quantidade de televisões.

2. **Variável Qualitativa Ordinal**:
   - **Definição**: Separa os indivíduos em classes com uma ordem específica.
   - **Exemplos**: Nível de escolaridade (fundamental, médio, superior).

3. **Variável Quantitativa Contínua**:
   - **Definição**: Expressa medidas como valores reais (podem assumir qualquer valor em um intervalo).
   - **Exemplos**: Peso, altura.

4. **Variável Qualitativa Nominal**:
   - **Definição**: Separa os indivíduos em classes, mas não há uma ordem específica.
   - **Exemplos**: Gênero, esporte praticado (futebol, basquete, ciclismo).

---

### Resumo das Alternativas

| Alternativa | Tipo de Variável | Explicação |
|-------------|------------------|------------|
| **A** | Quantitativa Discreta | Correta. Envolve contagens (números inteiros). |
| **B** | Qualitativa Ordinal | Errado. Descreve classes com ordem específica. |
| **C** | Quantitativa Contínua | Errado. Envolve medidas que podem assumir qualquer valor real. |
| **D** | Qualitativa Nominal | Errado. Descreve classes sem ordem específica. |

---
# Representação dos Dados Discretos

Considere a seguinte amostra de valores, relativos às disciplinas estudadas por 20 alunos do Gran Cursos Online:

\[
X = \{2, 8, 8, 6, 6, 8, 5, 5, 6, 7, 7, 7, 6, 6, 7, 5, 5, 7, 5, 5\}
\]

Esses valores são considerados **variáveis discretas**, pois são números inteiros. A partir deles, é possível formar tabelas para facilitar a compreensão.

---

## Passos para Construir uma Tabela de Frequência

### 1. Ordenar os dados  
Organize os valores em ordem crescente ou decrescente.

Exemplo:  

\[
X_{\text{ordenado}} = \{ 5, 5, 5, 5, 5, 5, 6, 6, 6, 6, 6, 7, 7, 7, 7, 7, 8, 8, 8\}
\]

### 2. Identificar os valores únicos  
Liste todos os valores distintos presentes na amostra.

\[
\text{Valores únicos} = \{ 5, 6, 7, 8\}
\]

### 3. Contar a frequência de cada valor  
Conte quantas vezes cada valor aparece na amostra.

- 5 aparece **6 vezes**.  
- 6 aparece **5 vezes**.  
- 7 aparece **5 vezes**.  
- 8 aparece **3 vezes**.  

### 4. Frequência Simples Absoluta (\( F_i \))  
A frequência simples absoluta representa o número de vezes que o elemento aparece no conjunto de dados.

### 5. Calcular a Frequência Relativa  
A frequência relativa é a razão entre a frequência absoluta e o número total de elementos.

Fórmula:

\[
Fr = \frac{Fa}{n}
\]

Exemplo:

\[
Fr(5) = \frac{6}{20} = 0,30 \quad \text{(ou 30%)}
\]

### 6. Calcular a Frequência Acumulada  
A frequência acumulada é o somatório das frequências absolutas até o valor atual.

Exemplo:

\[
Fac(6) = 6 (5) + 5 (6) = 12
\]

---

## Tabela de Frequência Completa

| Valor (\( x \)) | Frequência Simples Absoluta (\( F_i \)) | Frequência Absoluta (\( Fa \)) | Frequência Relativa (\( Fr \)) | Frequência Acumulada (\( Fac \)) |
|-----------------|----------------------------------------|--------------------------------|--------------------------------|----------------------------------|
| 5               | 6                                      | 6                              | 0,30 (30%)                     | 6                                |
| 6               | 5                                      | 5                              | 0,25 (25%)                     | 11                               |
| 7               | 5                                      | 5                              | 0,25 (25%)                     | 16                               |
| 8               | 3                                      | 3                              | 0,15 (15%)                     | 20                               |

---

## Interpretação da Tabela

- **Frequência Simples Absoluta (\( F_i \))**: Número de vezes que o valor aparece na amostra.  
- **Frequência Absoluta (\( Fa \))**: Número total de ocorrências para cada valor.  
- **Frequência Relativa (\( Fr \))**: Proporção de cada valor em relação ao total.  
- **Frequência Acumulada (\( Fac \))**: Soma das frequências absolutas até o valor atual.  

---

####Amplitude amostral Range
é a diferença entre o maior e o menor valor da amostra .
a aplitude se remete a auma idea de distancia , e para comprrender a ampliturede e tomado a base {4,8,8,6,6,8,5,5,5,5,6,7,8,6,5}
onde o maiorvalor é 8 e o menor valor é 4
a amplitude (A)= mairo valor - menor valor logo , 8 - 4 que é igual a 4



---

### Probabilidade

#### Definição
A probabilidade de um evento **A** é escrita como **P(A)**. 
Se **P(A) > P(B)**, então o evento **A** tem uma maior chance de ocorrer que o evento **B**.

- A probabilidade de um evento só pode estar entre **0** e **1**, ou seja:  
  \[
  0 \leq P(A) \leq 1
  \]

---

#### Exemplo Prático
Temos um saquinho com:
- 3 bolas amarelas,
- 2 bolas verdes,
- 2 bolas vermelhas,
- 1 bola azul.

**Resultados possíveis**:  
\[
\{ \text{amarelo, amarelo, amarelo, verde, verde, vermelho, vermelho, azul} \}
\]

- **Espaço amostral (S)**: Conjunto de todos os resultados possíveis.  
  Neste caso, o espaço amostral tem **8 elementos**.

---

#### Cálculo da Probabilidade
Queremos calcular a probabilidade de pegar uma bola **amarela**.

1. **Número de maneiras que o evento pode acontecer**:  
   Há **3 bolas amarelas**, então o evento "pegar uma bola amarela" pode acontecer de **3 maneiras**.

2. **Número total de resultados possíveis**:  
   O espaço amostral tem **8 resultados**.

3. **Fórmula da probabilidade**:  
   \[
   P(A) = \frac{\text{Número de maneiras que A pode acontecer}}{\text{Número total de resultados possíveis}}
   \]

4. **Aplicando os valores**:  
   \[
   P(\text{amarela}) = \frac{3}{8}
   \]

---

#### Resumo
- **Probabilidade de pegar uma bola amarela*:  
  \[
  P(\text{amarela}) = \frac{3}{8} = 0,375 \quad \text{(ou 37,5%)}
  \]

---

#### Cálculo da Probabilidade
Queremos calcular a probabilidade de pegar uma bola **verdes**.

1. **Número de maneiras que o evento pode acontecer**:  
   Há **2 bolas verdes**, então o evento "pegar uma bola verde" pode acontecer de **2 maneiras**.

2. **Número total de resultados possíveis**:  
   O espaço amostral tem **8 resultados**.

3. **Fórmula da probabilidade**:  
   \[
   P(A) = \frac{\text{Número de maneiras que A pode acontecer}}{\text{Número total de resultados possíveis}}
   \]

4. **Aplicando os valores**:  
   \[
   P(\text{verde}) = \frac{2}{8}
   \]

---

#### Resumo
- **Probabilidade de pegar uma bola verde**:  
  \[
  P(\text{verde}) = \frac{2}{8} = 0,25 \quad \text{(ou 25,0%)}
  \]

---

#### Exemplo Prático
Temos um saquinho com:
- 5 bolas amarelas,
- 2 bolas verdes,
- 3 bolas vermelhas,
- 4 bola azul.

---

#### Cálculo da Probabilidade
Queremos calcular a probabilidade de não  pegar uma bola que no seja  **azul**.

1. **Número de maneiras que o evento pode acontecer**:  
   Há **5 bolas amarelas, 2 bolas verdes, e 3 bolas vermelhas**, então o evento "não pegar uma bola azul" pode acontecer de **10 maneiras**.

2. **Número total de resultados possíveis**:  
   O espaço amostral tem **14 resultados**.

3. **Fórmula da probabilidade**:  
   \[
   P(A) = \frac{\text{Número de maneiras que A pode acontecer}}{\text{Número total de resultados possíveis}}
   \]

4. **Aplicando os valores**:  
   \[
   P(\text{todas as cores menos azul}) = \frac{10}{14}=0.714
   \]

---

#### Resumo
- **Probabilidade de pegar que não seja azul*:  
  \[
  P(\text{todas as cores menos azul}) = \frac{10}{14} = 0.71428571428
  \]
---

#### Exemplo 1: Probabilidade de não pegar uma bola azul
Temos um saquinho com:
- 3 bolas amarelas,
- 2 bolas verdes,
- 2 bolas vermelhas,
- 1 bola azul.

**Espaço amostral (S)**: 8 bolas no total.

- **Evento**: Não pegar uma bola azul.
- **Número de bolas que não são azuis**: 7 (3 amarelas + 2 verdes + 2 vermelhas).

**Cálculo**:
\[
P(\text{não azul}) = \frac{7}{8} = 0,875 \quad \text{(ou 87,5%)}
\]

---

#### Exemplo 2: Probabilidade de não tirar o valor 5 em um dado
Temos um dado honesto de 6 lados.

**Espaço amostral (S)**: 6 resultados possíveis (1, 2, 3, 4, 5, 6).

- **Evento**: Não tirar o valor 5.
- **Números que não são 5**: 1, 2, 3, 4, 6 (5 possibilidades).

**Cálculo**:
\[
P(\text{não 5}) = \frac{5}{6} \approx 0,83 \quad \text{(ou 83%)}
\]

---

#### Exemplo 3: Probabilidade de tirar uma carta preta de um baralho
Temos um baralho com:
- 3 cartas pretas,
- 7 cartas vermelhas.

**Espaço amostral (S)**: 10 cartas no total.

- **Evento**: Tirar uma carta preta.
- **Número de cartas pretas**: 3.

**Cálculo**:
\[
P(\text{carta preta}) = \frac{3}{10} = 0,30 \quad \text{(ou 30%)}
\]

---

#### Exemplo 4: Probabilidade de cair em uma área sombreada em uma roleta
Temos um círculo dividido em 5 partes iguais, das quais 2 áreas são sombreadas de azul.

**Espaço amostral (S)**: 5 partes no total.

- **Evento**: Cair em uma área sombreada.
- **Número de áreas sombreadas**: 2.

**Cálculo**:
\[
P(\text{área sombreada}) = \frac{2}{5} = 0,40 \quad \text{(ou 40%)}
\]

---

#### Exemplo 5: Probabilidade de cair em uma área que não é roxa em uma roleta
Temos um círculo dividido em 4 partes iguais, cada uma com uma cor diferente: roxo, rosa, verde e azul.

**Espaço amostral (S)**: 4 partes no total.

- **Evento**: Cair em uma área que não é roxa.
- **Número de áreas que não são roxas**: 3 (rosa, verde, azul).

**Cálculo**:
\[
P(\text{não roxo}) = \frac{3}{4} = 0,75 \quad \text{(ou 75%)}
\]

---

#### Exemplo 6: Probabilidade de Felipe ligar para uma pessoa da escola
Felipe tem 30 contatos no total, dos quais 16 são pessoas que ele conheceu na escola.

**Espaço amostral (S)**: 30 contatos no total.

- **Evento**: Ligar para uma pessoa da escola.
- **Número de contatos da escola**: 16.

**Cálculo**:
\[
P(\text{pessoa da escola}) = \frac{16}{30} \approx 0,53 \quad \text{(ou 53%)}
\]

---

### Resumo dos Exemplos
| Exemplo | Evento | Espaço Amostral | Número de Casos Favoráveis | Probabilidade |
|---------|--------|-----------------|----------------------------|---------------|
| 1       | Não pegar bola azul | 8 | 7 | \( \frac{7}{8} = 0,875 \) |
| 2       | Não tirar 5 no dado | 6 | 5 | \( \frac{5}{6} \approx 0,83 \) |
| 3       | Tirar carta preta | 10 | 3 | \( \frac{3}{10} = 0,30 \) |
| 4       | Cair em área sombreada | 5 | 2 | \( \frac{2}{5} = 0,40 \) |
| 5       | Não cair em roxo | 4 | 3 | \( \frac{3}{4} = 0,75 \) |
| 6       | Ligar para pessoa da escola | 30 | 16 | \( \frac{16}{30} \approx 0,53 \) |

---
Dos exemplos acima, verificamos que todo experimento ou fenômeno que envolva
um elemento casual terá seu modelo probabilístico especificado quando estabelecermos:
(a) um espaço amostral, Ω (chamado de omega), que consiste, no caso discreto, da enumeração (finita
ou infinita) de todos os resultados possíveis do experimento em questão:
Ω = {ω1, ω2, ..., ωn, ...}
(os elementos de Ω são os pontos amostrais ou eventos elementares);
(b) uma probabilidade, P(ω), para cada ponto amostral, de tal sorte que seja possível
encontrar a probabilidade P(A) de qualquer subconjunto A de Ω, isto é, a probabilidade do que chamaremos de um evento aleatório ou simplesmente evento.

Um experimento que pode fornecer diferentes resultados (contagens, medidas ou respostas) , muito embora seja repetido toda vez da mesma maneira.
Caracteriza:
A possibilidade de repetição sob as mesmas condições.
 Os resultados não são determinados a priori.
 Existência de regularidade quando o número de     repetições é grande. 
O conjunto de todos os resultados possíveis de um experimento aleatório é chamado de espaço amostral

---
# 📊 PROBABILIDADE E ESTATÍSTICA

## 🔍 O que é Estatística Inferencial?

A **Estatística Inferencial** é composta por métodos que usam uma **amostra aleatória (M.A.)** dos dados coletados de uma população para **descrever** e **fazer inferências sobre a população**.

Ela permite tirar conclusões sobre uma **população de interesse** com base em informações coletadas de uma **amostra**, e é amplamente usada em situações práticas do dia a dia.

### Principais técnicas da Inferência Estatística:
- **Estimação**
- **Teste de hipóteses**

---

## 🧪 Conceitos Fundamentais

### ✅ O que é uma população?
Conjunto completo de elementos (indivíduos, objetos, dados) sobre os quais se deseja obter informações ou fazer inferências.

### ✅ O que é uma amostra?
Subconjunto da população, selecionado de forma aleatória, usado para representar a população em análises estatísticas.

### ✅ O que é um parâmetro?
Valor numérico (fixo, mas geralmente desconhecido) que descreve uma característica da **população**.

<img src="https://fernandafperes.com.br/blog/intervalo-de-confianca/img2.png" width="300" height="200">
---

## 🎯 Estimativa Pontual

A **estimativa pontual** é um valor único calculado a partir de uma amostra, utilizado como a melhor suposição para um **parâmetro populacional**.

### Exemplo:
Queremos estimar a altura média dos alunos de uma escola. Selecionamos aleatoriamente 30 alunos e calculamos a média das alturas. Esse valor é uma **estimativa pontual** da média populacional.

| Parâmetro (População) | Significado                | Estimador (Amostra)           |
|------------------------|----------------------------|-------------------------------|
| **μ (mi)**             | Média populacional         | **\(\bar{x}\)** média amostral |
| **σ² (sigma²)**        | Variância populacional     | **\(S²\)** variância amostral  |
| **σ (sigma)**          | Desvio padrão populacional | **\(S\)** desvio padrão amostral |
| **p₀**                 | Proporção populacional     | **p** proporção amostral       |

> 🔹 **Estimador**: Variável aleatória que estima um parâmetro.  
> 🔹 **Estimativa**: Valor numérico específico obtido para uma determinada amostra.

---

## 📈 Distribuição Amostral

A **distribuição amostral** é a **distribuição de probabilidade** de um **estimador** (estatística) obtido a partir de várias amostras aleatórias extraídas da mesma população.

É representada por uma **função densidade de probabilidade (FDP)**.

### Exemplo visual:

<img src="https://www.researchgate.net/profile/Ben-Batista/publication/354194757/figure/fig1/AS:1134251848282114@1647438122776/Figura-9-Grafico-representativo-da-distribuicao-amostral-da-media-i-i-utilizado-na.ppm" width="300" height="200">

---

## 🔒 Intervalo de Confiança

É uma **faixa de valores**, calculada a partir da média amostral, que tem **alta probabilidade** de conter o verdadeiro valor da média da população.

- **Nível de confiança**: \(1 - \alpha\)  
  Ex: 95% → temos 95% de confiança de que o intervalo contém o parâmetro.
- **Erro**: \(\alpha\) é a **probabilidade** de o parâmetro estar fora do intervalo.

---

## 📉 Teorema do Limite Central (TLC)

O **TLC** afirma que:

> Dada uma amostra aleatória de tamanho suficientemente grande, com variáveis aleatórias \(X_1, X_2, ..., X_n\) independentes e identicamente distribuídas (i.i.d.), a **distribuição da média amostral** tende a uma distribuição **normal**, independentemente da distribuição original dos dados.

- Justifica o uso da **Normal** na inferência estatística.
- Quanto maior o tamanho da amostra, mais próxima da normal será a distribuição amostral.

---


### Referências
- [Capıtulo_2 Probabilidade](https://www.ime.usp.br/~rvicente/EST01_Probabilidade.pdf)
- [Distribuições Amostraise Estimação Pontual de Parâmetros](https://www.cin.ufpe.br/~rmcrs/ESAP/arquivos/cap07.pdf)
- [Khan Academy - Noções Básicas de Probabilidade](https://pt.khanacademy.org/math/em-mat-probabilidade/x37cb49a28da24b56:probabilidade/x37cb49a28da24b56:nocoes-basicas-de-probabilidade/v/basic-probability)
- [Livro: Probabilidade - Um Curso Moderno com Aplicações](https://z-library.sk/dl/3647248/f654b5)
- [Livro: Probabilidade e Estatística para Engenharia e Ciências](https://z-library.sk/dl/2528875/a95223)
- [Vídeo Aula - Gran Cursos Online](https://www.grancursosonline.com.br/aluno/curso/video/codigo/V3GmhgEULTQ%3D/v/8oEcakvbANQ%3D/c/E%2BeQFt%2Fioic%3D)
-[Livro pagina 60 probabilidade](https://reader.z-library.sk/read/3909c4415e82ece44dab3f35caed913ff7eaed64ea87a0db23020b8b649b74e1/2528875/616ab7/probalidade-e-estat%C3%ADstica-paraengenharia-e-ci%C3%AAncias.html?download_location=https%3A%2F%2Fz-library.sk%2Fdl%2F2528875%2Fa95223%3Fdsource%3Drecommend)
- [Aula 1 - USP](https://www.usp.br/gmab/discip/zab5711/aula1_slides.pdf)
- [Khan Academy - Estatística e Probabilidade](https://www.khanacademy.org/math/statistics-probability)
- [Vídeo Aula - YouTube](https://www.youtube.com/watch?v=sxQaBpKfDRk)
- [Toda Matéria - Estatística](https://www.todamateria.com.br/estatistica-conceito-fases-metodo/)
- [Brasil Escola - Estatística](https://brasilescola.uol.com.br/matematica/estatistica-2.htm)
- [Alura - Frequência Absoluta e Relativa](https://www.alura.com.br/artigos/frequencia-absoluta-e-relativa)
- [Provas de TI](https://www.provasdeti.com.br/cursos/001)
