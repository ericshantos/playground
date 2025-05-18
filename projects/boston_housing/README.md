[🇧🇷] [Lê em português](README.pt.md)

# 🏡 Predicting Home Values in Boston

<div style="display: flex; gap: 10px;">
    <a href="https://colab.research.google.com/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb">
        <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab" />
    </a>
    <a href="https://nbviewer.jupyter.org/github/ericshantos/playground/blob/main/projects/product_value_forecast/product_value_forecast.ipynb">
        <img src="https://img.shields.io/badge/Run%20in-Jupyter-orange" alt="Runs in Jupyter" />
    </a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License" />
    </a>
</div>

<br>

This project was developed to explore and create a **linear regression model** using the famous **Boston Housing dataset**. The main objective is to predict the **median home value (MEDV)** based on various regional characteristics such as crime rate, number of rooms, and proximity to employment centers. 🏘️📊

---

## 📝 Project Description

The notebook performs a comprehensive analysis of the Boston Housing dataset, from initial data exploration to building a predictive model. The focus is on understanding how different independent variables affect property values in Boston.

Key steps:
1. **Exploratory analysis** with correlation visualizations 🔍
2. **Data preprocessing** 🛠️
3. **Modeling** with linear regression 🧮
4. **Interpretation** of results 📈

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

## 📂 Data Structure

The dataset contains 506 observations and 15 columns, including:

### Key Variables:
- **CRIM**: Per capita crime rate
- **RM**: Average number of rooms per dwelling
- **DIS**: Weighted distances to employment centers
- **LSTAT**: % lower status population
- **MEDV**: Median home value (target variable)

Correlation analysis revealed that **RM** (0.695) and **LSTAT** (-0.738) are the variables most correlated with MEDV.

---

## 📊 Exploratory Analysis

Key insights:
- Correlation matrix and heatmap to identify variable relationships
- Distribution of home values (MEDV)
- Relationship between number of rooms (RM) and property values
- Impact of crime rate (CRIM) on housing values

---

## 🧠 Predictive Modeling

### Technique Used:
**Multiple Linear Regression** to predict MEDV based on multiple features.

General formula:
> MEDV = β₀ + β₁*CRIM + β₂*RM + β₃*DIS + ... + βₙ*LSTAT

### Evaluation Metrics:
- Coefficient of Determination (R²)
- Mean Squared Error (MSE)
- Mean Absolute Error (MAE)

---

## 🛠️ Technologies Used

- **Python** 🐍
- **Pandas** and **NumPy** for data manipulation
- **Matplotlib** and **Seaborn** for visualizations
- **Scikit-learn** for modeling
- **kagglehub** for dataset download

---

## 📈 Results and Conclusions

- The model demonstrated good accuracy in predicting home values
- Variables like number of rooms and socioeconomic status showed the greatest impact
- Correlation analysis was crucial for selecting relevant features

---

## 🚀 How to Use

1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Run the Jupyter notebook `boston_housing_forecast.ipynb`
4. Explore the data and experiment with model adjustments

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](https://opensource.org/licenses/MIT) file for details.