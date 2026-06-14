# Students Performance Analysis

> An exploratory data analysis investigating how demographic, socioeconomic, and preparation factors influence student academic performance across Math, Reading, and Writing tests.

[![Language](https://img.shields.io/badge/Language-Python%203.x-blue?style=flat-square)](https://www.python.org/)
[![Domain](https://img.shields.io/badge/Domain-Education%20Analytics-green?style=flat-square)]()
[![Dataset](https://img.shields.io/badge/Dataset-UCI%20Students%20Performance-orange?style=flat-square)]()

---

## Overview

This project analyzes the **UCI Students Performance in Exams** dataset (1,000 students) to understand how key background factors influence academic outcomes. Rather than just reporting averages, the analysis digs into **intersectional effects** — how multiple factors (e.g., gender × lunch type) compound to determine performance gaps — providing data-driven guidance for targeted educational interventions.

---

## Dataset

| Feature | Type | Values |
|---|---|---|
| Gender | Categorical | Male / Female |
| Race/Ethnicity | Categorical | Groups A – E |
| Parental level of education | Ordinal | Some high school → Master's degree |
| Lunch | Categorical | Standard / Free & Reduced |
| Test preparation course | Categorical | Completed / None |
| Math score | Numerical | 0 – 100 |
| Reading score | Numerical | 0 – 100 |
| Writing score | Numerical | 0 – 100 |

- **N = 1,000 students**
- No missing values
- Balanced gender split: ~482 female, ~518 male

---

## Analyses Performed

### 1. Gender vs. Subject Performance
- Male students score **significantly higher in Math** (avg ~69 vs. ~64 for females)
- Female students outperform males in both **Reading** (avg ~73 vs. ~66) and **Writing** (avg ~72 vs. ~63)
- Visualized using grouped bar charts and overlapping KDE distribution plots

### 2. Lunch Type Effect
- Students receiving **standard lunch** consistently outperform those on free/reduced lunch across all 3 subjects
- The effect is **strongest for Math scores** (avg difference ~12 points)
- Serves as a proxy for socioeconomic status — a significant predictor of academic outcomes

### 3. Parental Education Level
- Higher parental education correlates positively with all test scores
- Effect is **strongest for Reading and Writing** (language-heavy subjects)
- Students with parents holding a **Master's degree** average ~15 points higher in reading than those with "some high school"

### 4. Test Preparation Course Impact
- Students who **completed the test preparation course** score ~5–10 points higher on average across all subjects
- Improvement is most pronounced in Writing (+10.7 points average)
- Course completion rate: ~36% of students

### 5. Cross-Subject Correlation
- **Reading and Writing scores** are highly correlated (r ≈ 0.95) — near-linear relationship
- Math shows moderate correlation with Reading (r ≈ 0.82) and Writing (r ≈ 0.80)
- Heatmap confirms that strong readers are consistently strong writers

---

## Key Findings

> From the analysis:
> 1. **Gender effect is subject-specific:** Males lead in Math; females lead in language-based subjects
> 2. **Lunch type (socioeconomic proxy) is the strongest single predictor** of Math performance
> 3. **Parental education level** most strongly influences Reading and Writing outcomes
> 4. **Reading ↔ Writing scores are directly proportional** — nearly interchangeable metrics
> 5. Test preparation course provides a measurable but modest performance boost

---

## Visualizations

- Grouped bar charts (score by gender across subjects)
- Box plots (score distributions by parental education level)
- Heatmap (Pearson correlation matrix between all 3 test scores)
- Pie charts (test preparation course completion breakdown)
- Stacked bar charts (race/ethnicity group × average score)

---

## Getting Started

```bash
git clone https://github.com/tamer017/students-preformance.git
cd students-preformance
pip install pandas matplotlib seaborn jupyter
jupyter notebook
```

---

## Skills Demonstrated

`Exploratory Data Analysis` `Education Analytics` `Statistical Correlation` `Seaborn` `Matplotlib` `Pandas` `Socioeconomic Analysis` `Data Visualization` `Python` `Jupyter Notebook`
