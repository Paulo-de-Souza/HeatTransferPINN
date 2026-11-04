## Sobre a Aula

Esta aula é separada em duas frentes teóricas principais: Redes Neurais e PINNs. Recomenda-se que a leitura dos documentos seja feita na seguinte ordem:
1. Notebook **Aula_Fundamentos_RNN**
2. Arquivo **Aula_PINNsTranscal**
3. Como complemento, as aulas de **Variações de PINNs** e **PINNs aplicadas a MECSOL**

> Nota: A aula de PINNs em MECSOL é do conteúdo de uma disciplina da POSMEC e que foi lecionada com o Prof Dr. Wallace Gusmão em 2025.

## Parte Interativa do tópico de Redes Neurais

### Gradiente Descendente

[Abrir Animação Paraboloide](https://htmlpreview.github.io/?https://github.com/Paulo-de-Souza/HeatTransferPINN/blob/main/Aulas_Notebooks/Aula06/superficie_paraboloide.html)
<div align="left">
    <img src="https://raw.githubusercontent.com/Paulo-de-Souza/HeatTransferPINN/main/Images/figurasNN/Paraboloide.png"
    width="700">
</div>

[Abrir Animação Ackley](https://htmlpreview.github.io/?https://github.com/Paulo-de-Souza/HeatTransferPINN/blob/main/Aulas_Notebooks/Aula06/superficie_ackley.html)
<div align="left">
    <img src="https://raw.githubusercontent.com/Paulo-de-Souza/HeatTransferPINN/main/Images/figurasNN/Ackley.png"
    width="700">
</div>

## Glossário

### Estrutura da rede

| Termo | Definição |
|---|---|
| **Rede neural artificial** | Função parametrizada formada por neurônios organizados em camadas, capaz de aproximar relações entre entradas e saídas. |
| **Perceptron** | Unidade básica de uma rede neural que combina entradas usando pesos, adiciona um viés e aplica uma função de ativação. |
| **MLP** | Rede neural formada por várias camadas de perceptrons (*Multilayer Perceptron*). |
| **Peso** | Parâmetro que controla a influência de uma entrada ou conexão sobre a saída de um neurônio. |
| **Viés (*bias*)** | Parâmetro que desloca a resposta de um neurônio e permite ajustar sua ativação. |
| **Camada de entrada** | Camada que recebe as variáveis do problema. |
| **Camada oculta** | Camada intermediária responsável por realizar transformações sobre os dados. |
| **Camada de saída** | Camada que produz a previsão final da rede. |
| **Função de ativação** | Função não linear aplicada à saída de um neurônio, permitindo que a rede represente relações complexas. |
| **Rede totalmente conectada** | Rede em que cada neurônio de uma camada está conectado a todos os neurônios da camada seguinte. |
| **Rede profunda** | Rede que possui várias camadas ocultas. |

### Previsão e treinamento

| Termo | Definição |
|---|---|
| **Forward pass** | Caminho percorrido pelos dados desde a entrada até a saída da rede. |
| **Previsão** | Resultado produzido pela rede para uma determinada entrada. |
| **Função de perda (*loss function*)** | Função usada para medir o quanto as previsões se afastam dos valores de referência. |
| **MSE** | Erro quadrático médio, calculado pela média dos quadrados das diferenças entre os valores previstos e os valores de referência. |
| **Treinamento** | Processo de ajuste dos pesos e vieses para reduzir a função de perda. |
| **Parâmetros** | Valores aprendidos pela rede durante o treinamento, principalmente pesos e vieses. |
| **Gradiente** | Vetor que indica como a função de perda varia em relação aos parâmetros da rede. |
| **Gradiente descendente** | Método que atualiza os parâmetros na direção de redução da função de perda. |
| **Taxa de aprendizagem** | Hiperparâmetro que controla o tamanho dos passos realizados durante a atualização dos parâmetros. |
| **Regra da cadeia** | Regra do cálculo diferencial usada para obter derivadas de funções compostas. |
| **Retropropagação (*backpropagation*)** | Procedimento que aplica a regra da cadeia para calcular os gradientes dos pesos e vieses. |
| **Diferenciação automática** | Técnica que calcula derivadas aplicando a regra da cadeia às operações realizadas no programa. |
| **Otimizador** | Algoritmo que utiliza os gradientes para atualizar os parâmetros da rede. |
| **Adam** | Otimizador baseado em gradientes que adapta o tamanho do passo para cada parâmetro. |
| **L-BFGS** | Otimizador do tipo quase-Newton que utiliza informações de iterações anteriores para estimar a curvatura da função de perda. |

### Dados e configurações

| Termo | Definição |
|---|---|
| **Época** | Uma passagem completa pelo conjunto de dados de treinamento. |
| **Batch** | Grupo de amostras processadas antes de uma atualização dos parâmetros. |
| **Iteração** | Uma atualização dos parâmetros realizada após o processamento de um batch. |
| **Passo de otimização** | Uma atualização dos parâmetros pelo otimizador. |
| **Dados de treinamento** | Dados usados diretamente para ajustar os pesos e vieses da rede. |
| **Dados de validação** | Dados usados para acompanhar o desempenho e escolher configurações durante o desenvolvimento do modelo. |
| **Dados de teste** | Dados reservados para avaliar o desempenho final do modelo. |
| **Generalização** | Capacidade da rede de produzir boas previsões para exemplos que não foram usados no treinamento. |
| **Underfitting** | Situação em que a rede é simples demais ou pouco treinada para representar o problema. |
| **Overfitting** | Situação em que a rede se ajusta excessivamente aos dados de treinamento e apresenta desempenho ruim em dados novos. |
| **Normalização** | Transformação das variáveis para uma escala mais adequada ao treinamento. |
| **Hiperparâmetro** | Configuração definida pelo usuário, como número de camadas, número de neurônios, taxa de aprendizagem e número de épocas. |
| **Inicialização de pesos** | Estratégia usada para definir os valores iniciais dos pesos antes do treinamento. |
| **Glorot/Xavier** | Método de inicialização que busca manter a escala das ativações e dos gradientes estável entre as camadas. |
| **Superfície de perda** | Representação da função de perda em função dos parâmetros da rede. |
| **Mínimo local** | Ponto em que a perda é menor que nas regiões próximas, mas pode não ser o menor valor possível. |
| **Mínimo global** | Ponto correspondente ao menor valor da função de perda em todo o domínio considerado. |
