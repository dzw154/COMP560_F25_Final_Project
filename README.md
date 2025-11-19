# Nonlinear Factor Models in Financial Markets: A Comparative Study of Autoencoders and PCA

This project compares Principal Component Analysis (PCA) and neural autoencoders as factor models for financial return data. We focus on how well each method reconstructs returns and what structure their latent factors reveal.

## Goals
- Reduce the dimensionality of daily equity returns using PCA and an autoencoder  
- Compare reconstruction quality using R² and Mean Squared Error (MSE)  
- Cluster latent factors with K-means and compare groupings across methods  

## Data

We use daily prices from 2012–2025 for:

- S&P 500 index (\^GSPC)  
- Eight large tech stocks: AAPL, AMZN, GOOG, META, MSFT, NFLX, NVDA, TSLA  

Data is sourced via `yfinance` and Alpha Vantage, converted to log returns, and standardized before modeling.

## Methods

- **PCA**: Linear factors extracted from the return matrix, evaluated via per-asset R² and MSE.  
- **Autoencoder**: Feedforward encoder–decoder with a 128-neuron hidden layer and a low-dimensional bottleneck; evaluated with the same metrics.  
- **Clustering**: K-means with \(k = 3\) applied separately to PCA and autoencoder latent factors.

## Key Findings

- PCA is a strong baseline, especially for more linear or index-like series.  
- The autoencoder achieves competitive R² and MSE, and for some assets (e.g., NVDA, AAPL) matches or slightly exceeds PCA.  
- K-means on autoencoder factors reveals different groupings (e.g., TSLA with NFLX, META with NVDA), suggesting the nonlinear embedding captures relationships that PCA does not.

The full LaTeX report is available as `report.pdf` located in `report/report.pdf`.

Presentation slides are located in `presentation/Presentation Slides.pdf`.
* The link is also located in - https://docs.google.com/presentation/d/1ASH6VDv4nUTaEIOJqTpSyjirOToEHiGXF1dot4pq3uk/edit?usp=sharing
