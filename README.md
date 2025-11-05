# DataScienceCourse5_Project
**Electric Vehicle Data Analysis Using Python — DS PGC Course 5 Final Project**

---

## 📘 Project Overview
This project analyzes a dataset of **Electric Vehicles (EVs)** to extract insights about price, range, battery capacity, energy consumption, and performance.  
It combines **data analysis, visualization, and hypothesis testing** to guide decision-making and recommend optimal EV options.

**Dataset:** `FEV-data-Excel.xlsx`  
**Tools used:** Python (Pandas, NumPy, SciPy, Matplotlib, Seaborn, Jupyter Notebook)

---

## 🧩 Tasks Summary
1. **Filter EVs** below 350,000 PLN with ≥ 400 km range; group by manufacturer and compute average battery capacity.  
2. **Detect outliers** in energy consumption using the IQR method.  
3. **Visualize correlation** between battery capacity and range (scatterplot).  
4. **Build an EV recommendation class** that returns the top 3 EVs based on user input (budget, range, capacity).  
5. **Perform a two-sample t-test** comparing engine power of Tesla vs Audi vehicles.  
6. **Record a 5-minute video** summarizing findings (Drive link in notebook).

---

## 🧰 Tools & Libraries
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy.stats import ttest_ind
```
- **Pandas / NumPy:** data manipulation  
- **Matplotlib / Seaborn:** visualizations  
- **SciPy:** statistical inference  
- **OOP in Python:** custom EVRecommender class  
- **Jupyter Notebook:** stepwise analysis & documentation  

---

## 🧮 Example Code Snippets
```python
# Task 1 – Filter and aggregate
filtered = df[(df["Minimal price (gross) [PLN]"] <= 350000) &
              (df["Range (WLTP) [km]"] >= 400)]
avg_battery = filtered.groupby("Make")["Battery capacity [kWh]"].mean()

# Task 4 – Recommendation Class
class EVRecommender:
    def __init__(self, data): self.data = data
    def recommend(self, budget, min_range, min_battery):
        f = self.data[(self.data["Minimal price (gross) [PLN]"] <= budget) &
                      (self.data["Range (WLTP) [km]"] >= min_range) &
                      (self.data["Battery capacity [kWh]"] >= min_battery)]
        return f.sort_values(by="Range (WLTP) [km]", ascending=False).head(3)
```

---

## 📊 Insights & Results
- **Outliers:** None detected in energy consumption range.  
- **Range vs Battery:** Strong positive correlation.  
- **Top EVs (by range ≤ 350 k PLN):** Tesla Model 3 Long Range, Tesla Model 3 Performance, VW ID.3 Pro S.  
- **T-test (Tesla vs Audi engine power):**  
  - *p-value ≈ 0.106* → not statistically significant.  
  - Tesla mean = 533 KM, Audi = 392 KM → Tesla higher average but variation large.  
- **Recommendation:** Focus on improving affordability & mid-range performance.

---

## 📂 Files Included
- `DataScienceCourse5ProjectProblemStatement.pdf` — Project brief  
- `DataScienceCourse5ProjectSolutionPDFForm.pdf` — Final solution report (PDF)  
- `DataScienceCourse5SolutionPythonNotebook.ipynb` — Executable notebook  
- *(Dataset link inside notebook)*  

---

## 🧭 How to Review
1. Open the Jupyter Notebook (`.ipynb`) to view code, visuals, and analysis.  
2. Review the report PDF for summary + screenshots.  
3. Check the included Google Drive video link in the notebook for oral walkthrough.  

---

## 👤 Author
**Utkarsh Anand** — DS PGC Course 5 Final Project  
Internshala Placement Guarantee Program
