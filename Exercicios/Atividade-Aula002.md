### Exercícios - Preparação de Dados

## 1. Importância da Preparação de Dados

# Resposta:

A qualidade do modelo depende totalmente da qualidade dos dados, se a base de entrada tiver ruidos,
inconsistencias ou escalas desproporcionais, até o algoritmo mais avançado vai entregar resultados ruins.

## 2. Valores Ausentes

# Resposta:

a. Podemos excluir as linhas com falhas ou preencher esses buracos usando a média da coluna, ou até criar
um modelo preditivo para estimar valores.
b. Remover registros não é o ideal quando isso causa uma perda massiva de informações ou quando a própria
ausência do dado tiver algum significado importante para o problema

## 3. Normalização vs Padronização

# Resposta:

A Normalização comprime os valores para caberem em um intervalo fixo, de 0 a 1. A Padronização ajusta os dados
para que fiquem com média 0 e desvio padrão 1. Qualquer uma das duas é obrigatória em algoritmos baeados em
distância, garantindo que variáveis com grandezas maiores não dominem o cálculo.

## 4. Dados Categóricos

# Resposta:

a. A melhor forma é usar técnicas como o One-Hot Encoding.
b. Usar apenas números (0, 1 e 2) faz o algoritmo assumir erroneamente que existe uma ordem de grandeza
ou hierarquia entre as categorias.

## 5. Overfitting e Separação de Dados

# Resposta:

O conjunto de treino faz o modelo aprender, o de validação serve para calibrar os hiperparâmetros, e o de teste
avalia a performance final. Se usarmos os dados de teste no treinamento, ocorre vazamento de dados, o que resulta
em métricas de sucesso irreais e mascaradas.

## 6. Balanceamento de Classes

a. O modelo fica enviesado, para manter uma precisão alta, ele simplesmente vai viciar e tender a prever quase
sempre a classe majoritária.
b. Podemos aplicar Oversampling para gerar mais dados de classe menor, Undersampling para cortar dados de classe
maior, ou usar o ajuste de pesos nas classes.

## 7. Detecção de Outliers

# Resposta:

a. São dados anômalos ou valores extremos que desviam muito do padrão geral do dataset.
b. Se a remoção for feita sem critério, podemos acabar apagando dados de eventos que são raros, mas reais e cruciais
para o modelo.
c. O cálculo do Z-score ou o método estatistico IQR.

## 8. Feature Engineering

# Resposta:

Transformar a data em idade entrega um valor numérico direto que o algoritmo consegue interpretar e usar de cara, eliminando
a complexidade de processar formatos de tempo e calendário.

## 9. Pipeline de Pré-processamento

# Resposta:

O Fluxo ideal seria nesta ordem: Tratar os valores ausentes -> aplicar codificação nos dados categóricos -> escalonar as variáveis
com diferentes grandezas -> aplicar técnicas de balanceamento de classes -> fazer o split dividindo os dados em conjuntos de treino, validação e teste

## 10. Estudo de Caso Aplicado – Crédito Bancário

# Resposta:

As etapas seriam:

1. Checar inconsistências nos dados e preencher/remover valores ausentes
2. Codificar a variável categórica estado_civil usando One-Hot Enconding
3. Escalonar as variáveis continuas que possuem grandezas diferentes
4. Analisar se há desbalanceamento de classes e aplicar técnicas de correção
5. Dividir o dataset em conjutos de treino, validação e teste antes de rodar qualquer coisa
