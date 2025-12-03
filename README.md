# STATS-507-Final-Project

This project is designed for short-term realized volatility forecasting using high-frequency limit-order-book and trade data from the Optiver Kaggle competition. The workflow includes data understanding, feature engineering, model development, and feature-importance analysis.

# Part 1 — Data Understanding
In this section, we examine the structure of the Kaggle dataset, which links order-book and trade parquet files to 428,932 (stock_id, time_id) pairs. We summarize the distribution of realized volatility, highlight its heavy-tailed and asymmetric nature, and discuss why these properties motivate flexible, non-Gaussian modeling approaches.

# Part 2 — Feature Engineering
Here, we construct an extended set of predictors from weighted average prices, log returns, realized volatilities, spreads, imbalances, and various statistical descriptors. We further aggregate these features across 150-, 300-, and 450-second forward windows to capture short-horizon temporal dynamics, resulting in approximately 240 engineered features.

# Part 3 — LightGBM and SVM Implementation
In this part, we develop and evaluate the predictive models:
LightGBM is used to capture nonlinear interactions and microstructure-driven patterns.
Linear SVM identifies stable linear relationships within the high-dimensional feature set.
A Meta-LightGBM stacking model combines the outputs of both learners, evaluated through 5-fold cross-validation using RMSPE.

# Part 4 — Feature Importance
In the final section, we show that LightGBM and SVM rely on largely distinct sets of features, with minimal correlation between their importance profiles. LightGBM emphasizes diverse nonlinear and temporal factors, whereas SVM concentrates on realized-volatility summaries. This non-overlapping feature usage supports the effectiveness of the stacking approach and explains the observed performance gains.
