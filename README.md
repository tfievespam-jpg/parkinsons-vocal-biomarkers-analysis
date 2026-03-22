# Parkinson's Disease Severity Prediction
OLS regression on vocal biomarkers — built from scratch with NumPy
 
---
 
## Question
Can a voice recording predict how severe a Parkinson's patient's motor symptoms are?
 
## Dataset
UCI Parkinson's Telemonitoring (ID 189) — 5,875 recordings, 42 patients.  
Target: `motor_UPDRS` (motor symptom severity score).  
Citation: Tsanas, Little, McSharry & Ramig (2009), IEEE Transactions on Biomedical Engineering.
 
## Methodology
- Standardization + removal of perfectly collinear features
- VIF filter (threshold > 10) to keep only independent biomarkers
- OLS via Normal Equation: β̂ = (XᵀX)⁻¹Xᵀy — no ML library
 
## Results
| Metric | Value |
|---|---|
| R² | 0.092 |
| RMSE | 7.746 |
| Top predictor | PPE — Pitch Period Entropy |
 
Vocal biomarkers alone explain 9% of motor severity variance. PPE is the only robust positive predictor after multicollinearity correction.
 
## Run
```bash
pip install numpy pandas matplotlib seaborn scipy ucimlrepo
jupyter notebook parkinsons_ols.ipynb
```
 
## Author
**Thibault Fieve** — Dual MS Finance & Business Analytics Hult Boston | MIT MicroMasters in Statistics & Data Science - [LinkedIn](https://linkedin.com/in/thibault-fieve-data)
