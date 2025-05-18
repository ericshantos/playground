<h1 align='center'>🧑‍💻 Modelo de Previsão de Dígitos Manuscritos (MNIST)</h1>

<div style="display: flex; justify-content: center; gap: 10px; margin-bottom: 20px;">
    <a href="https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/MNIST_Predictor/MNIST_Predictor.ipynb">
        <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Abrir no Colab" />
    </a>
    <a href="https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/MNIST_Predictor/MNIST_Predictor.ipynb">
        <img src="https://img.shields.io/badge/Run%20in-Jupyter-orange" alt="Executar no Jupyter" />
    </a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="MIT License" />
    </a>
</div>

<div style="text-align: center;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/2/27/MnistExamples.png" alt="MNIST Sample" style="max-width: 100%; height: auto;" />
</div>

Este projeto implementa um modelo de Rede Neural Convolucional (CNN) para classificação de dígitos manuscritos utilizando o conjunto de dados MNIST. O modelo alcança uma acurácia de **98.52%** no conjunto de teste.

## 📝 Descrição do Projeto

O projeto consiste em um classificador de dígitos manuscritos (0-9) que utiliza:

- **TensorFlow/Keras** para construção e treinamento do modelo
- **Redes Neurais Convolucionais** (CNN) como arquitetura principal
- **Pré-processamento** de imagens em escala de cinza (28x28 pixels)
- **Avaliação de desempenho** com métricas de acurácia

Principais etapas:
1. Carregamento e pré-processamento dos dados
2. Construção da arquitetura CNN
3. Treinamento do modelo
4. Avaliação e visualização de resultados
5. Salvamento do modelo treinado

## 🛠️ Tecnologias Utilizadas

- Python 3.x
- TensorFlow 2.x
- Keras
- NumPy
- Matplotlib

## 🚀 Execução

Para executar este projeto localmente, siga os passos abaixo:

1. Instale as dependências listadas no arquivo `requirements.txt`:

```bash
pip install -r requirements.txt
```

2. Inicie o Jupyter Lab para abrir e executar o notebook:

```bash
jupyter lab
```

## 📂 Estrutura do Código

```bash
MNIST_Predictor/
├── MNIST_Predictor.keras       # Modelo treinado salvo
└── MNIST_Predictor.ipynb       # Notebook com implementação completa
```

## 🧠 Arquitetura do Modelo

O modelo utiliza a seguinte arquitetura CNN:

```python
model = models.Sequential([
    layers.Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    layers.MaxPooling2D((2,2)),
    
    layers.Conv2D(64, (3,3), activation='relu'),
    layers.MaxPooling2D((2,2)),
    
    layers.Conv2D(128, (3,3), activation='relu'),
    layers.MaxPooling2D((2,2)),
    
    layers.Flatten(),
    layers.Dense(128, activation='relu'),
    layers.Dropout(0.4),
    
    layers.Dense(10)
])
```

## 📊 Resultados

| Métrica         | Desempenho |
|-----------------|------------|
| Acurácia (train)| 99.2%      |
| Acurácia (test) | 98.52%     |
| Loss (test)     | 0.0421     |

## 📄 Licença

Distribuído sob licença MIT. Veja [LICENSE](./../../LICENSE) para mais informações.
