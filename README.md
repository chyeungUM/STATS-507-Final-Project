# STATS-507-Final-Project

This project focuses on short-term volatility forecasting using high-frequency order-book and trade data from the Optiver Kaggle competition. The dataset contains detailed bid/ask prices, sizes, and transaction records for 112 stocks across more than 428k time intervals.
To model short-horizon volatility, the project builds an extensive feature set derived from weighted average prices, log returns, realized volatilities, and multi-window aggregations (150, 300, 450 seconds). These engineered features capture both microstructure dynamics and forward-looking temporal patterns.
Two complementary models are used: LightGBM for nonlinear and interaction effects, and Linear SVM for stable linear relationships in high-dimensional space. A stacked meta-LightGBM model combines their outputs and is evaluated using RMSPE with 5-fold cross-validation. The stacked approach provides consistent improvements over both base models and naive benchmarks.
