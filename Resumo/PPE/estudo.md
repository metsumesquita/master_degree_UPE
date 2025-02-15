# Concurso Público: Noções de Estatística e Probabilidade

## Referências
- [Aula 1 - USP](https://www.usp.br/gmab/discip/zab5711/aula1_slides.pdf)
- [Khan Academy - Estatística e Probabilidade](https://www.khanacademy.org/math/statistics-probability)
- [Vídeo Aula - YouTube](https://www.youtube.com/watch?v=sxQaBpKfDRk)
- [Toda Matéria - Estatística](https://www.todamateria.com.br/estatistica-conceito-fases-metodo/)
- [Brasil Escola - Estatística](https://brasilescola.uol.com.br/matematica/estatistica-2.htm)
- [Alura - Frequência Absoluta e Relativa](https://www.alura.com.br/artigos/frequencia-absoluta-e-relativa)
- [Provas de TI](https://www.provasdeti.com.br/cursos/001)

---

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

### Exercício
Sobre estatística aplicada, é correto o que se afirma em?

- **a**: Parâmetros são medidas características de grupos. **(Incompleto)**

---


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


### Referências Adicionais
- [Khan Academy - Noções Básicas de Probabilidade](https://pt.khanacademy.org/math/em-mat-probabilidade/x37cb49a28da24b56:probabilidade/x37cb49a28da24b56:nocoes-basicas-de-probabilidade/v/basic-probability)
- [Livro: Probabilidade - Um Curso Moderno com Aplicações](https://z-library.sk/dl/3647248/f654b5)
- [Livro: Probabilidade e Estatística para Engenharia e Ciências](https://z-library.sk/dl/2528875/a95223)
- [Vídeo Aula - Gran Cursos Online](https://www.grancursosonline.com.br/aluno/curso/video/codigo/V3GmhgEULTQ%3D/v/8oEcakvbANQ%3D/c/E%2BeQFt%2Fioic%3D)
-[Livro pagina 60 probabilidade](https://reader.z-library.sk/read/3909c4415e82ece44dab3f35caed913ff7eaed64ea87a0db23020b8b649b74e1/2528875/616ab7/probalidade-e-estat%C3%ADstica-paraengenharia-e-ci%C3%AAncias.html?download_location=https%3A%2F%2Fz-library.sk%2Fdl%2F2528875%2Fa95223%3Fdsource%3Drecommend)
