# Context-Aware AI System for NBA Statline Forecasting

This repository contains the full software implementation for a context-aware AI system that predicts NBA player statlines (Points, Rebounds, Assists).

---

## AI Framing

This system can be interpreted as an **intelligent agent**:

- **Percepts:** pregame contextual features (usage, matchup, availability)
- **Actions:** predicted statlines (PTS, REB, AST)
- **Objective:** minimize prediction error (MAE)

The environment is **partially observable and stochastic**, making this a decision-making problem under uncertainty.

---

## Dataset

- ~52,707 player-game observations  
- 694 players  
- ~2,460 games  
- Data sourced via `nba_api`

Data is generated dynamically through notebooks.

---

## Models

- Linear Regression (baseline)
- Random Forest
- XGBoost (best model)

Best performance (XGBoost V4):
- PTS MAE: ~2.195
- REB MAE: ~0.908
- AST MAE: ~0.602

---

## Pipeline

The system follows an AI pipeline:

1. Data acquisition (nba_api)
2. Feature representation (context-aware features)
3. Model training
4. Evaluation on future data
5. Deployment as inference system

---

## How to Run

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Streamlit Demo

After installing dependencies, run the deployment app from the project root:

```bash
streamlit run deployment/app.py