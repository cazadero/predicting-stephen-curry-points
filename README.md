# 🏀 Stephen Curry Next-Game Points Predictor

### 🎓 A Personal Machine Learning Project by **Danny Le**

---

## 📌 Overview

This project combines two of my passions, **data science** and **basketball**. Using the `nba_api`, I built a machine learning model to predict how many points **Stephen Curry** will score in his next game, based only on data that would be available *before tip-off*. 

The challenge was not only predicting his points, which can be volatile, but also ensuring the model didn’t cheat by accessing future data. This created a truly deployable and safe workflow.

---

## 🎯 Objective

> **"Can we predict Curry's point total in his next game using his recent performances and the context of the upcoming matchup?"**

To answer that, I created a time-aware dataset that includes:

- Curry’s last 12 seasons (2013-14 through 2024-25) of game-by-game stats
- Rolling averages of his recent performance (past 5 games)
- Defensive rankings of the opponent *up to* game day
- Home/away splits, rest days, and back-to-backs
- Time-series cross-validation for model evaluation

---

## 🔧 Tech Stack

- **Python** (Pandas, NumPy, Matplotlib)
- **Scikit-learn** (Ridge Regression, Cross-Validation, Pipelines)
- **NBA API** (`nba_api`)
- **Modeling Approach**: Ridge Regression

---

## 📊 Model Performance

- ✅ **Best MAE (Ridge Regression):** `6.49` points
- 📉 Benchmark (predicting 5-game rolling average): ~`7.71` points
- 📈 Predicted vs Actual points are **reasonably aligned**, but the model tends to:
  - Overpredict during low-scoring games
  - Underpredict during explosive, high-scoring games

---

## 💡 Key Features Engineered

| Feature              | Description |
|----------------------|-------------|
| `IS_HOME`            | 1 if Curry plays at home |
| `HOME_AND_REST`      | 1 if rested AND playing at home |
| `BACK_TO_BACK`       | 1 if playing games with 0 or 1 day rest between |
| `MIN_PLAYER_ROLL5`   | Average minutes (last 5 games) |
| `FGM_PLAYER_ROLL5`   | Average field goals made (last 5 games) |
| `PTS_PLAYER_ROLL5`   | Average points (last 5 games) - used only for baseline |

Along with opponent team rankings like:
- Opponent’s `PTS_RANK`, `FG3M_RANK`, `TOV_RANK`, `PLUS_MINUS_RANK`, etc.

---

## 🔍 Takeaways

- Building a *realistic and deployable* ML pipeline involves more than just modeling. I had to prevent data leakage, align game contexts, and carefully merge historical NBA data.
- Even though 6.49 MAE isn't state-of-the-art, it beat the baseline I calculated and shows how much signal can be pulled from past performance and opponent context.
- This project taught me:
  - Time series validation
  - Feature engineering with sports data
  - Rolling statistics & performance trends
  - How to evaluate and visualize real-world ML output

---

## 🚀 Next Steps

- 🔁 Add **XGBoost** and **Random Forest** models for non-linear learning
- 🧠 Test classification approach (predicting scoring ranges, not exact points)
- 🏗️ Expand to other players or team-wide models

---

## 📬 Contact

**Danny Le**  
[📧 Email](mailto:dannyle05@berkeley.edu)  
[🔗 LinkedIn](https://www.linkedin.com/in/dannyle510)
