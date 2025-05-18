<h1 align='center'>🧑‍💻 Handwritten Digit Prediction Model (MNIST)</h1>

<div style="display: flex; justify-content: center; gap: 10px; margin-bottom: 20px;">
    <a href="https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/MNIST_Predictor/MNIST_Predictor.ipynb">
        <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab" />
    </a>
    <a href="https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/MNIST_Predictor/MNIST_Predictor.ipynb">
        <img src="https://img.shields.io/badge/Run%20in-Jupyter-orange" alt="Run in Jupyter" />
    </a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="MIT License" />
    </a>
</div>

<div style="text-align: center;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/2/27/MnistExamples.png" alt="MNIST Sample" style="max-width: 100%; height: auto;" />
</div>

This project implements a Convolutional Neural Network (CNN) model to classify handwritten digits using the MNIST dataset. The model achieves an accuracy of **98.52%** on the test set.

## 📝 Project Description

The project is a handwritten digit classifier (0-9) that uses:

* **TensorFlow/Keras** for building and training the model
* **Convolutional Neural Networks** (CNN) as the core architecture
* **Preprocessing** of grayscale images (28x28 pixels)
* **Performance evaluation** using accuracy metrics

Main steps:

1. Load and preprocess the data
2. Build the CNN architecture
3. Train the model
4. Evaluate and visualize results
5. Save the trained model

## 🛠️ Technologies Used

* Python 3.x
* TensorFlow 2.x
* Keras
* NumPy
* Matplotlib

## 🚀 Execution

To run this project locally, follow the steps below:

1. Install the specific dependencies in the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

2. Start Jupyter Lab to open and run the notebook:

```bash
jupyter lab
```

## 📂 Code Structure

```bash
MNIST_Predictor/
├── MNIST_Predictor.keras       # Saved trained model
└── MNIST_Predictor.ipynb       # Notebook with complete implementation
```

## 🧠 Model Architecture

The model uses the following CNN architecture:

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

## 📊 Results

| Metric           | Performance |
| ---------------- | ----------- |
| Accuracy (train) | 99.2%       |
| Accuracy (test)  | 98.52%      |
| Loss (test)      | 0.0421      |

## 📄 License

Distributed under the MIT License. See [LICENSE](./../../LICENSE) for more information.
