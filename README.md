# Deep Learning para Reconhecimento de Doenças Respiratórias através de Raios-X

Este repositório contém o código para uma aplicação de deep learning que é capaz de reconhecer doenças respiratórias a partir de imagens de raios-X. O programa utiliza um modelo de Rede Neural Convolucional (CNN) com a arquitetura ResNet50 pré-treinada para a classificação de imagens.

## Configuração do Ambiente

- Python 3.6+
- TensorFlow 2.x
- OpenCV
- NumPy
- Matplotlib
- Seaborn
- scikit-learn

## Preparação dos Dados

O dataset utilizado é montado através do Google Drive e processado utilizando o `ImageDataGenerator` do TensorFlow para aumentar e normalizar as imagens. As classes de doenças respiratórias reconhecidas são:

- COVID-19
- Normal
- Pneumonia Viral
- Pneumonia Bacteriana

## Modelo

O modelo é construído com base na arquitetura ResNet50 com as seguintes adaptações:

- Adição de camadas de Average Pooling, Flatten, Dense e Dropout.
- A camada de saída é uma Dense com ativação softmax para classificação em 4 classes.
- O treinamento é feito com a função de perda `categorical_crossentropy` e otimizador RMSprop.

## Treinamento

- O treinamento é executado por 25 épocas com callbacks para salvar os melhores pesos.
- Os resultados do treinamento são visualizados por gráficos de acurácia e perda.

## Avaliação e Teste

- O modelo é avaliado usando um conjunto de teste separado e a acurácia é calculada.
- Uma matriz de confusão e um relatório de classificação são gerados para análise de desempenho.
- O modelo é testado com imagens individuais para predição.

## Uso

Para usar o modelo com suas próprias imagens de raios-X:

1. Carregue o modelo treinado `weights.hdf5` (localizado na pasta modelo do diretório) com `load_model`.
2. Prepare suas imagens de entrada para ter o tamanho correto e normalizado.
3. Faça a predição utilizando o modelo carregado.
4. A classe prevista é retornada juntamente com a probabilidade.

## Contribuição

Sinta-se livre para clonar, modificar e usar este código em seus próprios projetos de reconhecimento de imagem médica.

## Licença MIT

Esse projeto está sob a licença MIT. Isso significa que você pode reutilizar e modificar o código, desde que inclua um aviso de direitos autorais original e não utilize o código para fins comerciais sem permissão. Para mais informações, consulte o arquivo `LICENSE` incluso neste repositório.

---

*Nota: É essencial que você tenha permissão e respeite as regulamentações de privacidade e ética ao usar e compartilhar dados médicos.*
