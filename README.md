# rt-lifestyle-mlr
> Statistical exploration of reaction time as a cognitive health indicator using multiple linear regression across lifestyle and demographic factors.

---

## 🧠 Overview
This repository presents a quantitative cross-sectional analysis investigating how **daily screen exposure**, **stress level**, **sleep duration**, and **age** influence **reaction time (RT)** — a key measure of cognitive processing speed.

Using **multiple linear regression (MLR)**, the project examines whether these behavioural and demographic factors significantly explain differences in RT. The findings suggest weak linear relationships, indicating that cognitive performance may depend on more complex, nonlinear interactions.

---

## ⚙️ Methods
- **Design:** Quantitative, cross-sectional  
- **Model:** Multiple Linear Regression (OLS)  
  \[
  RT = \beta_0 + \beta_1(Age) + \beta_2(Sleep) + \beta_3(Stress) + \beta_4(ScreenTime) + \varepsilon
  \]
- **Diagnostics:** Scatter plots, residual vs fitted plots, Q–Q plot, Durbin–Watson, Levene’s test, Omnibus & Jarque–Bera for normality.

---

## 📊 Results Summary
- **F-statistic:** 1.452 (p = 0.215) → fail to reject \(H_0\)
- **R²:** 0.007 → Model explains only 0.7% of variation in RT  
- **Adjusted R²:** 0.002 → negligible explanatory power  
- **Durbin–Watson:** 1.977 → no autocorrelation  
- **Levene’s p-value:** 0.277 → homoscedastic  
- **Omnibus p = 0.000, Jarque–Bera p < 0.001** → residuals not normal  

➡️ These results suggest that **linear relationships are weak or absent**, and nonlinear or threshold effects may better explain cognitive performance patterns.

---

## 🧩 Reproducibility
- **Sample size:** 800 (from full dataset using `random_state=42`)
- **Libraries:** pandas, numpy, statsmodels, matplotlib, seaborn  
- **Python version:** 3.10+

To reproduce:
```bash
# Clone the repo
git clone https://github.com/<your-username>/rt-lifestyle-mlr.git
cd rt-lifestyle-mlr

# Create environment
python -m venv .venv
source .venv/bin/activate   # or .venv\Scripts\activate on Windows
pip install -r requirements.txt

# Run scripts
python src/sample_data.py
python src/eda.py
python src/model.py
