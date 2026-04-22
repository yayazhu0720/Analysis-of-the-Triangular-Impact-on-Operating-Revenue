# Analysis-of-the-Triangular-Impact-on-Operating-Revenue
A multiple linear regression-based template for revenue health diagnosis: quantifying how historical total assets, ROA, and leverage impact operating revenue for enterprises.
## Overview
This project is based on the multiple linear regression model. It is constructed with the historical data of A-share enterprises as the foundation, and a revenue health diagnosis template is created to quantitatively analyze the specific impacts of the three core indicators - total assets, ROA, and debt-to-asset ratio - on the company's revenue. Through regression analysis, the direction and intensity of the influence of each factor are output, providing data-based operational diagnosis basis for enterprises. The project can be directly reused to help enterprises clearly identify how key operating elements affect revenue and provide objective references for business decisions.
## Research objective
The project is based on the general rules extracted from the A-share market. Enterprises can refer to the regression results of the overall market, compare their own indicator performances, and determine the actual contribution of each operating factor to the revenue. Thus, they can achieve an objective diagnosis of the revenue driving structure and provide quantitative basis for business decisions.
## Variable Definitions
- **Dependent Variable `y`**: Operating Revenue, representing the scale of a firm’s core business performance.
- **Independent Variable `x1`**: Total Assets, used to test the scale effect on operating revenue.
- **Independent Variable `x2`**: Return on Assets (ROA), measuring how asset profitability impacts operating revenue.
- **Independent Variable `x3`**: Asset-Liability Ratio, examining the relationship between leverage and operating revenue.

The model uses OLS regression with HC3 robust standard errors to address potential heteroskedasticity, ensuring the reliability of the coefficient estimates.
## Regression Results & Conclusions
The OLS regression analysis of A-share listed firms yields the following key findings:
1.  **Model Fit**: The model achieves an R-squared of 0.765, indicating that the three variables together explain approximately 76.5% of the variation in operating revenue. The F-statistic is statistically significant at the 1% level (p < 0.001), confirming the overall validity of the model.
2.  **Significant Drivers of Operating Revenue**:
    - `x1 (Total Assets)`: Shows a positive and highly significant coefficient (0.8947, p < 0.001). This indicates that, holding other factors constant, an increase in total assets is associated with a substantial rise in operating revenue, reflecting a strong scale effect.
    - `x2 (ROA)`: Also exhibits a positive and statistically significant coefficient (2.1841, p < 0.001). This suggests that higher asset profitability is strongly linked to greater operating revenue, highlighting the critical role of operational efficiency in driving top-line growth.
3.  **Non-significant Leverage Effect**:
    - `x3 (Asset-Liability Ratio)`: The coefficient (-0.0021) is not statistically significant (p = 0.994). This implies that, on average, leverage level does not have a clear linear impact on operating revenue in the sample.
4.  **Robustness**: HC3 robust standard errors were used to control for heteroskedasticity, ensuring the reliability of the significance tests.

### Figure 1: Box Plots of Variable Distributions
Figure 1 presents box plots of the core variables. Logarithmic transformations are applied to total assets and operating revenue to address skewness in the raw financial data.

![Box Plots](https://github.com/user-attachments/assets/8a8f45ed-b73c-44ad-a89f-62d2926a885e)

---

### Figure 2: Regression Coefficient Comparison
Figure 2 compares the magnitude of the estimated coefficients. ROA shows the strongest positive impact on operating revenue, followed by total assets. Leverage ratio does not show a significant effect.

![Coefficient Plot](https://github.com/user-attachments/assets/3ba0d268-827f-4446-95aa-4451728622bd)

---

### Figure 3: Variable Correlation Heatmap
The correlation heatmap confirms that the independent variables have low pairwise correlations, ensuring the regression model is not affected by severe multicollinearity.

![Correlation Heatmap](https://github.com/user-attachments/assets/9beca0f4-89b9-4ac5-9e28-67538b1da45d)

## Usage

### 1. Environment Requirements
- Python 3.8 or higher
- A valid WRDS account (for accessing the dataset)

### 2. Install Dependencies
Install all required libraries using:
```bash
pip install -r requirements.txt   
