# NBA Team Performance & Scheduling Analysis  
**Advanced Regression | Sports Analytics | NBA API**

**Authors:** Phuong Trinh 

---

## 📌 Project Overview
This project examines how **NBA scheduling factors**—specifically **travel distance, rest days, and back-to-back games**—influence team performance and win probability across the **2023–2025 NBA regular seasons**.

Using game-level data extracted from the **NBA API**, we combine engineered schedule-based fatigue metrics with traditional basketball performance statistics to evaluate whether schedule burden meaningfully affects outcomes once on-court efficiency is accounted for.

---

## 🎯 Problem Motivation
NBA teams face demanding travel schedules, compressed game calendars, and uneven rest patterns. These factors raise important questions about **player fatigue, competitive fairness, and schedule design**. While schedule effects are often discussed qualitatively, they are less frequently quantified relative to core performance metrics.

This project aims to measure the **true predictive value of scheduling variables** compared to in-game performance indicators when modeling win probability.

---

## 🔍 Research Questions
- Do travel distance and rest days significantly affect win probability?
- Are back-to-back games associated with worse performance outcomes?
- How does home-court advantage interact with fatigue-related factors?
- Which regression approach best balances interpretability and predictive accuracy?

---

## 📊 Data & Feature Engineering
- **Data Source:** NBA API (game logs)
- **Seasons Covered:** 2023–2025
- **Observations:** 4,920 team–game records
- **Workflow:** Python (API extraction) → CSV → R (analysis & modeling)

### Engineered Features
- **Scheduling / Fatigue**
  - Travel distance (computed from arena coordinates)
  - Rest days between games
  - Back-to-back game indicator
- **Contextual**
  - Home vs. away indicator
  - Opponent strength
- **Performance**
  - FG%, 3PT%, FT%
  - Rebounds, assists, turnovers
  - Plus/minus and points

---

## 🧹 Data Preparation
- Standardized variable names and formats
- Removed duplicates and inconsistent records
- Handled missing values using domain-informed rules
- Identified extreme values in travel distance and applied **winsorization**
- Scaled continuous variables using **z-score normalization**
- Encoded win/loss and schedule indicators for regression modeling

---

## 📈 Exploratory Data Analysis
EDA focused on understanding both **league-wide trends** and **team-level disparities**, including:
- Back-to-back frequency and average rest days by season
- Differences in scheduling burden across teams
- Correlation structure between scheduling variables and performance metrics

Results showed that:
- Shooting efficiency and plus/minus are strongly correlated with wins
- Scheduling variables exhibit weaker, more subtle relationships
- Multicollinearity among schedule variables is low

---

## 🤖 Modeling Approach
- **Baseline Model:** Logistic Regression
- **Model Selection:** AIC & BIC for variable reduction
- **Regularized Models:** Ridge and Lasso regression

Logistic regression provided interpretability but showed signs of overfitting due to dominant performance metrics. Ridge and Lasso were used to improve stability and generalization while controlling model complexity.

---

## 📊 Results & Model Performance
- **Key Drivers of Win Probability:**
  - FG% and 3PT%
  - Rebounds and turnovers
  - Home-court advantage
- **Scheduling Effects:**
  - Travel distance, rest days, and back-to-back games had weak or insignificant effects once performance metrics were included
- **Best Performing Models:**
  - Ridge and Lasso achieved **AUC ≈ 0.87**
  - Regularization reduced overfitting and improved robustness

---

## 🧠 Key Insight
> **On-court execution overwhelmingly outweighs scheduling burden in predicting NBA game outcomes.**  
While rest and travel matter operationally, **performance efficiency remains the dominant factor driving wins**.

---

## 🛠 Tech Stack
- **Languages:** Python, R  
- **Tools & Libraries:**
  - NBA API
  - dplyr, ggplot2
  - glm, Ridge, Lasso
  - caret, pROC
  - Plotly (interactive scheduling visualization)

---

## 🚀 Future Work
- Build scheduling-only models to isolate pure fatigue effects
- Incorporate player-level workload and injury data
- Explore nonlinear models (Random Forest, XGBoost)
- Add advanced travel context (time zones, altitude, travel direction)
- Extend analysis to playoff scheduling effects

