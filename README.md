
# Machine Learning the Spectrum of X-ray Binaries

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  

**Predicting $\log(N_H)$ and $\Gamma$ from X-ray Colours using Machine Learning**

---

## 📘 What is this repository?

This repository contains the full code and analysis accompanying the project _Machine Learning the Spectrum of X-ray Binaries_. The goal of the study is to explore whether X-ray colours, derived from Chandra X-ray Observatory data, can be used to infer two key spectral parameters:

- **$\log(N_H)$**: Logarithm of the hydrogen column density
- **$\Gamma$**: Photon index describing the slope of the intrinsic X-ray spectrum

We evaluate three machine learning regressors—Polynomial Regression, K-Nearest Neighbors (KNN), and Random Forest Regression (RFR)—to learn this mapping from colour space to physical parameters.

📝 **You can read the full report [here](https://github.com/elizabethbirchhardwick/Machine_Learning_the_Spectrum_of_X-ray-Binaries/blob/main/X_ray_binaries.pdf).**

---

## 📜 License  
This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.  

When using this code, please:  
- Retain the original license/copyright notice.  
- Attribute by linking back to this repository (e.g., `Machine Learning the Spectrum of X-ray Binaries by Elizabeth Birch Hardwick`).  

---

## 📁 Repository structure

```
📄 main.ipynb                         # Main Jupyter Notebook
📄 LICENSE                            # MIT License file
📄 points_results_cycle3.csv          # Data used to train model (Cycle 3)
📄 points_results_current_cycle.csv   # Data used to train model (Cycle 25)
📄 train3.csv                         # Train data for train-test split used in article (Cycle 3)
📄 test3.csv                          # Test data for train-test split used in article (Cycle 3)
📄 train25.csv                        # Train data for train-test split used in article (Cycle 25)
📄 test25.csv                         # Test data for train-test split used in article (Cycle 25)
📄 poly_coefficients_cycle3.csv       # Exported polynomial regression coefficients (Cycle 3)
📄 poly_coefficients_cycle25.csv      # Exported polynomial regression coefficients (Cycle 25)
📄 use_coefficients_example.ipynb     # Notebook demonstrating how to use exported coefficients
📄 README.md                          # This file
```

---
## 📓 Usage

Open the main notebook:

```bash
git clone https://github.com/elizabethbirchhardwick/Machine_Learning_the_Spectrum_of_X-ray-Binaries.git
cd Machine_Learning_the_Spectrum_of_X-ray-Binaries
pip install -r requirements.txt
jupyter notebook main.ipynb
```

Inside the notebook, you'll find:

- 📊 **Data generation and visualization**
- 🤖 **Training and cross-validating three ML models**
- 🔁 **Cycle comparison (Cycle 3 vs Cycle 25)**
- 🧽 **Error filtering by removing high-uncertainty regions**
- 📈 **Visual evaluation using scatter and MAE contour plots**
- 🧮 **Model interpretation and coefficient export**

All output cells are pre-run for convenience, but feel free to rerun and experiment!

---

## 📤 Using the Polynomial Coefficients CSV

We trained polynomial regression models on both **Cycle 3** and **Cycle 25** datasets. The learned coefficients and bias terms for each were exported to CSV files:

- `poly_coefficients_cycle3.csv`
- `poly_coefficients_cycle25.csv`

These files allow you to reconstruct predictions for $\log(N_H)$ and $\Gamma$ manually or in other programming environments:

1. Import new values of **H** and **S** (hard and soft colours).
2. Use the same polynomial expansion (same degree) as in the notebook.
3. Apply the formula $\text{prediction} = \text{bias} + \sum_{i=1}^n \text{coef}_i \cdot \text{feature}_i$

To simplify this process, we also include a helper notebook:

```bash
jupyter notebook use_coefficients_example.ipynb
```

This notebook demonstrates how to load the CSV files and use them to compute predictions step by step.

---

## 💬 Support

For questions or suggestions, feel free to reach out:

📧 **elizabethbirchhardwick@gmail.com**  
🚀 Or open an issue on [GitHub](https://github.com/elizabethbirchhardwick/Machine_Learning_the_Spectrum_of_X-ray-Binaries/issues)




