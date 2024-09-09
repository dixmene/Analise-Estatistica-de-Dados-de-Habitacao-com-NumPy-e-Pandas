## Projeto: Análise Estatística com NumPy e Pandas

### 1. Descrição do Projeto

O projeto visa realizar operações matemáticas e estatísticas em um dataset utilizando ferramentas como NumPy e Pandas. As principais atividades incluem o cálculo de estatísticas básicas, manipulação de dados e operações com matrizes.

### 2. Dataset Utilizado

**Nome do Dataset:** Ames Housing Data

**Descrição:** O dataset contém informações sobre imóveis em Ames, Iowa, incluindo características como a idade da casa, número de quartos, população e renda média.

**Exemplo de Dados:**

| longitude | latitude | housing_median_age | total_rooms | total_bedrooms | population | households | median_income | median_house_value | ocean_proximity |
|-----------|----------|--------------------|-------------|----------------|------------|------------|---------------|--------------------|-----------------|
| -122.23   | 37.88    | 41.0               | 880.0       | 129.0          | 322.0      | 126.0      | 8.3252        | 452,600.0          | NEAR BAY        |
| -122.22   | 37.86    | 21.0               | 7,099.0     | 1,106.0        | 2,401.0    | 1,138.0    | 8.3014        | 358,500.0          | NEAR BAY        |

### 3. Objetivos do Projeto

- **Calcular Estatísticas Básicas:** Determinar as médias, medianas e modos para variáveis selecionadas para compreender a distribuição e características dos dados.
- **Realizar Operações Aritméticas:** Obter soma e desvio padrão para entender a magnitude e a variabilidade das variáveis.
- **Executar Operações em Matrizes:** Realizar multiplicação e inversão de matrizes para explorar as relações entre variáveis e aplicar conceitos matemáticos.

### 4. Resultados Obtidos

#### Estatísticas Básicas

**Código:**

```python
import pandas as pd

# Carregar o dataset
file_path = r'C:\Users\Daniel\Desktop\Projetos Portifolio milanote\Linguagens\python\Cálculo de Estatísticas Básicas com NumPy\AmesHousing.csv'
df = pd.read_csv(file_path)

# Cálculo das estatísticas básicas
mean_values = df[['total_rooms', 'total_bedrooms', 'population', 'households', 'median_income']].mean()
median_values = df[['total_rooms', 'total_bedrooms', 'population', 'households', 'median_income']].median()
mode_values = df[['total_rooms', 'total_bedrooms', 'population', 'households', 'median_income']].mode().iloc[0]

print("Médias:\n", mean_values)
print("Medianas:\n", median_values)
print("Modos:\n", mode_values)
```

**Médias:**

- Total Rooms: 2,635.76
- Total Bedrooms: 532.48
- Population: 1,425.48
- Households: 499.54
- Median Income: 3.87

**Medianas:**

- Total Rooms: 2,127.00
- Total Bedrooms: 435.00
- Population: 1,166.00
- Households: 409.00
- Median Income: 3.53

**Modos:**

- Total Rooms: 1,527.00
- Total Bedrooms: 280.00
- Population: 891.00
- Households: 306.00
- Median Income: 3.13

#### Operações Aritméticas

**Código:**

```python
import numpy as np

# Cálculo da soma
sum_values = df[['total_rooms', 'total_bedrooms', 'population', 'households', 'median_income']].sum()

# Cálculo do desvio padrão
std_dev = df[['total_rooms', 'total_bedrooms', 'population', 'households', 'median_income']].std()

print("Soma:\n", sum_values)
print("Desvio Padrão:\n", std_dev)
```

**Soma:**

- Total Rooms: 54,402,150.0
- Total Bedrooms: 10,990,309.0
- Population: 29,421,840.0
- Households: 10,310,499.0
- Median Income: 79,890.65

**Desvio Padrão:**

- Total Rooms: 2,181.56
- Total Bedrooms: 422.67
- Population: 1,132.43
- Households: 382.32
- Median Income: 1.90

#### Operações em Matrizes

**Código:**

```python
import numpy as np

# Definir matrizes
total_rooms = np.array(df['total_rooms'])
total_bedrooms = np.array(df['total_bedrooms'])

# Multiplicação de Matrizes
matrix_product = np.outer(total_rooms, total_bedrooms)

# Inversão de Matrizes (exemplo com matriz 2x2)
matrix = np.array([[1, 2], [3, 4]])
matrix_inverse = np.linalg.inv(matrix)

print("Produto das Matrizes:\n", matrix_product)
print("Matriz Inversa:\n", matrix_inverse)
```

**Multiplicação de Matrizes (Total Rooms x Total Bedrooms):**

O produto das matrizes total_rooms e total_bedrooms mostra a interação entre essas variáveis. Esse produto pode ser utilizado para entender interações complexas entre variáveis.

**Inversão de Matrizes:**

- **Matriz Original:**

  ```
  [[1, 2],
   [3, 4]]
  ```

- **Matriz Inversa:**

  ```
  [[-2.0, 1.0],
   [1.5, -0.5]]
  ```
  
---

## Interpretação dos Resultados

### Estatísticas Básicas

**Médias:**
- **Total Rooms:** 2,635.76  
  Imóveis geralmente têm muitos quartos.
- **Total Bedrooms:** 532.48  
  O número médio de dormitórios reflete imóveis grandes.
- **Population:** 1,425.48  
  Indica uma densidade populacional moderada.
- **Households:** 499.54  
  O número médio de lares sugere áreas residenciais bem estabelecidas.
- **Median Income:** 3.87  
  Renda média moderada.

**Medianas:**
- Os valores menores que as médias indicam a presença de imóveis com características extremas, como muitos quartos ou rendas altas.

**Modos:**
- Os valores mais frequentes mostram padrões comuns, como a quantidade típica de quartos e dormitórios.

### Operações Aritméticas

**Soma:**
- **Total Rooms:** 54,402,150  
  Reflete a grandeza geral dos dados.
- **Population:** 29,421,840  
  Alta concentração de habitantes.
- **Median Income:** 79,890.65  
  Total acumulado de rendas.

**Desvio Padrão:**
- **Total Rooms:** 2,181.56  
  Grande variabilidade no número de quartos.
- **Population:** 1,132.43  
  Variação significativa na população entre os imóveis.

### Operações em Matrizes

**Multiplicação de Matrizes:**
- Ajuda a entender interações entre características dos imóveis (quartos e dormitórios).

**Inversão de Matrizes:**
- Conceito fundamental para análises mais complexas e modelagem.
  
---

### 5. Gráficos

**Gráfico das Médias das Variáveis:**

```python
import pandas as pd
import matplotlib.pyplot as plt

# Carregar o dataset
file_path = r'C:\Users\Daniel\Desktop\Projetos Portifolio milanote\Linguagens\python\Cálculo de Estatísticas Básicas com NumPy\AmesHousing.csv'
df = pd.read_csv(file_path)

# Calcular médias
mean_values = df[['total_rooms', 'total_bedrooms', 'population', 'households', 'median_income']].mean()

# Criar gráfico
plt.figure(figsize=(10, 6))
mean_values.plot(kind='bar', color='skyblue')
plt.title('Médias das Variáveis')
plt.xlabel('Variáveis')
plt.ylabel('Média')
plt.xticks(rotation=45)
plt.grid(axis='y', linestyle='--', alpha=0.7)
plt.tight_layout()

# Salvar gráfico
plt.savefig(r'C:\Users\Daniel\Desktop\Projetos Portifolio milanote\Linguagens\python\Cálculo de Estatísticas Básicas com NumPy\grafico_medias.png')
plt.show()
```
![image](https://github.com/user-attachments/assets/39c213cd-0843-42c2-9660-095701ba3f1b)


**Distribuição de Total Rooms e Total Bedrooms:**

```python
import pandas as pd
import matplotlib.pyplot as plt

# Carregar o dataset
file_path = r'C:\Users\Daniel\Desktop\Projetos Portifolio milanote\Linguagens\python\Cálculo de Estatísticas Básicas com NumPy\AmesHousing.csv'
df = pd.read_csv(file_path)

# Criar gráfico de distribuição
plt.figure(figsize=(12, 6))

# Gráfico de Total Rooms
plt.subplot(1, 2, 1)
plt.hist(df['total_rooms'], bins=50, color='lightcoral', edgecolor='black')
plt.title('Distribuição de Total Rooms')
plt.xlabel('Total Rooms')
plt.ylabel('Frequência')

# Gráfico de Total Bedrooms
plt.subplot(1, 2, 2)
plt.hist(df['total_bedrooms'], bins=50, color='lightseagreen', edgecolor='black')
plt.title('Distribuição de Total Bedrooms')
plt.xlabel('Total Bedrooms')
plt.ylabel('Frequência')

plt.tight_layout()

# Salvar gráfico
plt.savefig(r'C:\Users\Daniel\Desktop\Projetos Portifolio milanote\Linguagens\python\Cálculo de Estatísticas Básicas com NumPy\grafico_distribuicao.png')
plt.show()
```
![image](https://github.com/user-attachments/assets/4b595688-637d-463f-b466-c446fcf2a17b)


### 6. Conclusão

Este projeto demonstrou a aplicação de operações básicas e avançadas com NumPy e Pandas para a análise de dados. Através da análise estatística, foi possível extrair insights valiosos e compreender melhor as variáveis envolvidas, possibilitando decisões mais informadas e um entendimento mais profundo do dataset.

---
