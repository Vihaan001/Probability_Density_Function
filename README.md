# 🟡 Parameter Estimation using Roll-Number-Parameterized Non-Linear Model

![Python](https://img.shields.io/badge/Python-3.12-FFE135?style=for-the-badge&logo=python&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-black?style=for-the-badge&logo=jupyter&logoColor=FFE135)
![Data Science](https://img.shields.io/badge/Data_Science-Estimation-FFE135?style=for-the-badge&logo=scipy&logoColor=black)

## ⚡ Overview
[cite_start]This repository contains a Python implementation for learning probability density functions using a non-linear model[cite: 27]. [cite_start]The project processes the India Air Quality dataset, specifically isolating Nitrogen Dioxide (NO2) as the primary feature ($x$)[cite: 28].

**Author:** Vihaan Agarwal
**Roll Number:** 102303658

---

## 💻 Methodology

### 1. Data Transformation
[cite_start]Each $x$ value from the NO2 dataset is transformed into $z$ using the following parameterized function[cite: 31, 33]:
$$z = T_r(x) = x + a_r \sin(b_r x)$$

[cite_start]The coefficients $a_r$ and $b_r$ are dynamically generated using my university roll number ($r = 102303658$) via modulo operations[cite: 34, 35]:
* $a_r = 0.05 \times (r \pmod 7) = \mathbf{0.1}$
* $b_r = 0.3 \times ((r \pmod 5) + 1) = \mathbf{1.2}$

### 2. Parameter Estimation
[cite_start]The transformed data $z$ is then fitted to the following probability density function (PDF)[cite: 36, 37]:
$$\hat{p}(z) = c \cdot e^{-\lambda(z-\mu)^2}$$

[cite_start]Using Maximum Likelihood Estimation (MLE) concepts for a normal distribution, the parameters $\lambda$, $\mu$, and $c$ were derived from the transformed dataset[cite: 39].

---

## 📊 Results & Parameters
[cite_start]Based on the data transformation and subsequent estimation, the final learned parameters are[cite: 40]:

| Parameter | Symbol | Calculated Value |
| :--- | :---: | :--- |
| **Mean** | $\mu$ | `25.80743` |
| **Lambda** | $\lambda$ | `0.00146` |
| **Normalization Constant** | $c$ | `0.02155` |

### Visualization
Below is the visualization mapping the histogram of the transformed data against the fitted continuous probability density curve:

![Probability Density Function Fit](./pdf_fit_graph.png)

---

## 🗄️ Repository Contents
* `Assignment_1_102303658.ipynb`: The primary Jupyter Notebook containing the data loading, transformation logic, and mathematical modeling.
* `data.csv`: The India Air Quality dataset.
* `pdf_fit_graph.png`: High-resolution plot comparing the actual data distribution with the fitted curve.

> [cite_start]**Dataset Reference:** > Source: [India Air Quality Data on Kaggle](https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data)[cite: 29].
