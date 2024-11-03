# Classificação de Imagens com PyTorch

## Descrição do Projeto
Este repositório contém um mini-projeto de classificação de imagens utilizando PyTorch. O objetivo é treinar um modelo de rede neural para classificar imagens em diferentes categorias, avaliar o desempenho do modelo e demonstrar as predições em um conjunto de teste. O projeto inclui métricas e visualizações para facilitar a análise do desempenho do modelo.

## Estrutura do Repositório
Pytorch.ipynb: Notebook que contem as seções de treinamento e predição. A seção de treinamento realiza o treinamento do modelo de classificação de imagens, incluindo etapas de pré-processamento, treinamento e validação. Essa seção também salva os pesos do melhor modelo (best_model.pth) durante o treinamento. A seção de predição serve para carregar o modelo treinado e realizar predições no conjunto de teste, além de gerar métricas e gráficos de desempenho.
best_model.pth: Arquivo contendo os pesos do melhor modelo treinado, usado na parte de predição.
data/: Diretório opcional onde o dataset de treino e teste será armazenado (configurado automaticamente pelo PyTorch ao baixar o dataset).

## Dataset
Para este projeto, foi utilizado o dataset CIFAR-10, composto por 60.000 imagens de 32x32 pixels em 10 classes diferentes, com 6.000 imagens por classe. O dataset está dividido em 50.000 imagens para treinamento e 10.000 imagens para teste. Cada imagem pertence a uma das seguintes classes:
* Classes: Avião, Automóvel, Pássaro, Gato, Cervo, Cachorro, Sapo, Cavalo, Navio, Caminhão.
O CIFAR-10 foi escolhido por ser amplamente utilizado em projetos de visão computacional, permitindo avaliar o modelo em um conjunto diverso de categorias.

## Pré-processamento
As etapas de pré-processamento incluem:
1. Normalização: Aplicada para padronizar os valores dos pixels com média 0.5 e desvio padrão 0.5 em cada canal RGB.
2. Transformação para Tensor: As imagens foram convertidas para tensores PyTorch para serem processadas pelo modelo.

## Modelo
O modelo utilizado é uma Rede Neural Convolucional Simples (CNN) com duas camadas convolucionais e duas camadas totalmente conectadas. A arquitetura é adequada para capturar as características das imagens de baixa resolução do CIFAR-10, e o modelo foi treinado para minimizar a função de perda CrossEntropyLoss usando o otimizador Adam.

## Como Executar
* Requisitos
Para executar os notebooks, instale as seguintes dependências:
  ** pip install torch torchvision matplotlib scikit-learn

## Treinamento do Modelo
1. Abra o notebook Pytorch.ipynb.
2. Execute todas as células na parte de treinamento para treinar o modelo no dataset CIFAR-10.
3. Durante o treinamento, o notebook salva os pesos do melhor modelo no arquivo best_model.pth.

## Predição com o Modelo Treinado
1. Certifique-se de que o arquivo best_model.pth (pesos do modelo) está no mesmo diretório que o notebook.
2. Execute todas as células da parte de predição para gerar as métricas de desempenho e visualizar os resultados no conjunto de teste.

## Avaliação e Métricas
As métricas utilizadas para avaliar o desempenho do modelo incluem:
* Acurácia: Proporção de predições corretas sobre o total de amostras.
* F1 Score: Média harmônica entre precisão e recall, calculada para cada classe e depois agregada.
* Matriz de Confusão: Exibe as predições corretas e incorretas para cada classe, facilitando a identificação de possíveis padrões de erro.

## Gráficos de Desempenho
Durante o treinamento e validação, foram gerados gráficos para:
* Acurácia de Treinamento e Validação: Mostra a evolução da acurácia do modelo ao longo das épocas.
* Loss (Erro) de Treinamento e Validação: Monitora a função de perda, permitindo avaliar se o modelo está convergindo.
* Matriz de Confusão: Exibida no notebook de predição, para análise detalhada do desempenho em cada classe.

## Resultados
O modelo foi avaliado no conjunto de teste, atingindo uma acurácia de aproximadamente 75% e um F1 Score médio de aproximadamente 0.74, o que indica uma performance razoável considerando a simplicidade da arquitetura. A matriz de confusão revelou que o modelo teve mais dificuldades em distinguir entre classes com características visuais similares, como gatos e cães.
* Resultados durante o treinamento:
![image](https://github.com/user-attachments/assets/c8df8727-03f3-42a3-9f99-d05dbda71677)
![image](https://github.com/user-attachments/assets/1a35a3fb-232d-40ac-b39b-a24bb8cea7ef)
![image](https://github.com/user-attachments/assets/5f745491-a0f9-4d28-82e3-85a912d5f950)
![image](https://github.com/user-attachments/assets/7d5c9241-66b0-4c0e-9ed3-cd244cda19b1)

  
* Resultados durante a predição:
![image](https://github.com/user-attachments/assets/b1ee7356-e9ae-432a-96b2-eb9c8e8d1993)
![image](https://github.com/user-attachments/assets/da464a58-4eb1-43fe-83b3-971e306cd459)
![image](https://github.com/user-attachments/assets/78ea3906-dfd7-426e-a573-bfdb32602874)
![image](https://github.com/user-attachments/assets/fd96e74a-2a49-4325-8890-12b82a3fd183)


## Conclusão
Este projeto demonstrou a implementação de um classificador de imagens simples usando PyTorch, com foco na construção de um pipeline completo de treinamento, avaliação e predição. Melhorias no modelo podem ser exploradas usando arquiteturas mais complexas ou técnicas de aumento de dados.
