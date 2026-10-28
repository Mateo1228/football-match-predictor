⚽ Football Match Predictor

Probabilistic forecasting of football match outcomes (home win / draw / away win and goals) for the Premier League and UEFA Champions League, benchmarked against the betting market.

🚧 Work in progress — built step by step and documented publicly. Follow the roadmap below to see where the project stands.

Why this project

Betting odds are a market: they aggregate information into prices. A forecasting model is only useful if it can match or beat that market. This project asks a simple question:

Can a transparent statistical model produce match probabilities as well-calibrated as the closing odds?

The same toolkit (probabilities, time series, honest backtesting against a market benchmark) applies directly to energy and commodity markets, which is the longer-term direction of my work.

Approach
Explore historical results and odds.
Baseline: naive predictions (e.g. "home team always wins") and market-implied probabilities.
Model: team attack/defence strengths → expected goals → Poisson model → 1X2 probabilities.
Evaluate: walk-forward backtest (no look-ahead), scored with Brier score and log loss vs. baseline and market.
Improve: time-weighting (Dixon-Coles), expected goals (xG) inputs, gradient boosting.
Publish: weekly pre-match predictions with a public track record.
Roadmap
 Step 1 — Load and explore Premier League data (home advantage, goals per match)
 Step 2 — Goal distributions vs. Poisson
 Step 3 — Convert odds into implied probabilities (removing the bookmaker margin)
 Step 4 — Naive baseline + evaluation metrics (Brier score, log loss)
 Step 5 — Poisson model from team attack/defence strengths
 Step 6 — Walk-forward backtest vs. baseline and market
 Step 7 — Clean notebooks and documented results
 Step 8 — First public pre-match predictions
 Step 9 — Time-weighted model (Dixon-Coles)
 Step 10 — Expected goals (xG) as model input
 Step 11 — Gradient boosting model (XGBoost / LightGBM)
 Step 12 — Weekly automated pipeline + Streamlit dashboard (Premier League + Champions League)
Results

Coming soon. Model performance vs. baseline and market will be reported here as each step is completed.

Repository structure
football-match-predictor/
├── notebooks/
│   └── paso01_explorar_premier.ipynb   # Step 1: data exploration
├── data/                               # (ignored) raw downloads
├── src/                                # reusable code (from step 5 onward)
└── README.md
Data
football-data.co.uk — historical results and betting odds
Planned: Understat (xG), StatsBomb Open Data (event data)

All data is used for non-commercial, educational purposes and credited to its original sources.

Tech stack

Python · pandas · NumPy · SciPy · scikit-learn · matplotlib · Google Colab

About me

Mateo Peñuela — Civil & Geosciences Engineer, MSc Geo-Energy with Machine Learning and Data Science at Imperial College London. I build machine learning projects at the intersection of sports and commodity markets.

LinkedIn

Disclaimer: this project is for research and educational purposes only. It is not betting or financial advice.
