# 📊 Portfolio Optimization & Black–Litterman Model in Excel

![Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Finance](https://img.shields.io/badge/Domain-Quantitative_Finance-blue?style=for-the-badge)
![Institution](https://img.shields.io/badge/University-University_of_Colombo-red?style=for-the-badge)

An end-to-end quantitative portfolio engineering model built in **Microsoft Excel**. The project applies **Modern Portfolio Theory (MPT)** alongside the **Black–Litterman Framework** across 10 major U.S. equities to construct risk-optimized investment allocations, perform Monte Carlo price simulations, and incorporate subjective investor views into asset return expectations.

---

## 📌 Project Overview

Traditional **Markowitz Modern Portfolio Theory (MPT)** often produces extreme asset weights and is highly sensitive to input return estimations. The **Black–Litterman Model** solves this by starting with CAPM market equilibrium returns and blending them with subjective investor views using Bayesian probability to produce stable, optimal portfolio weights.

### **Key Highlights**
- **10 Major U.S. Equities Analyzed:** Tesla, Sony ADR, Morgan Stanley, Broadcom, Apple, Alphabet (Google), NVIDIA, Mastercard, Meta Platforms, and ASML ADR.
- **Benchmarking:** Calibrated against 10-Year U.S. Treasury yield data ($R_f$) and S&P 500 returns ($R_m$).
- **Advanced Excel Analytics:** Covariance/correlation matrix validation, Cholesky Decomposition, stochastic Monte Carlo price simulations, and Solver-based optimization.

---

## 🛠️ Quantitative Methodologies & Mechanics

### 1. Return & Risk Calibration
- Computed **Daily & Annual Logarithmic Returns** $\ln\left(\frac{P_t}{P_{t-1}}\right)$ to achieve additivity and normality.
- Calculated asset Betas ($\beta$) against S&P 500 benchmark indices.
- Established risk-free rate ($R_f$) from 10-Year U.S. Treasury yield data.

### 2. Matrix Algebra & Positive Definiteness
- Formulated $10 \times 10$ **Daily and Annualized Covariance Matrices** ($\Sigma$) and Correlation Matrices.
- Verified **Positive Definiteness** of the variance-covariance matrix to ensure validity for matrix operations.

### 3. Stochastic Simulation (Monte Carlo)
- Executed **Cholesky Decomposition** ($L \cdot L^T = \Sigma$) on the annual covariance matrix to convert independent standard normal random deviates ($Z$) into correlated normal random deviates ($C$).
- Simulated multi-path future price trajectories and return distributions across the asset universe.

### 4. Modern Portfolio Theory (MPT) & Efficient Frontier
- Generated random portfolio weight distributions to simulate thousands of portfolio risk-return pairs.
- Solved for the **Minimum Volatility Portfolio** using Excel Solver under long-only weight constraints ($\sum w_i = 1, w_i \ge 0$).
- Plotted the **Efficient Frontier** mapping risk (annualized volatility $\sigma_p$) against expected annual return ($E(R_p)$).

### 5. Black–Litterman Model Integration
- **Market Implied Equilibrium Returns ($\Pi$):** Derived baseline return distributions using market-cap weights and the risk aversion coefficient ($\lambda$).
- **Investor Views Setup:** Formulated relative and absolute investor views (e.g., *NVIDIA outperforming Apple by 8% annually*, *Broadcom outperforming Morgan Stanley by 6%*).
- **Posterior Return & Weight Calculation:** Combined market equilibrium ($\Pi$) with views ($Q$) weighted by uncertainty ($\Omega$) to obtain updated posterior return expectations and optimized allocations.

---

## 📁 Workbook Structure

The Excel workbook (`CS3_17545.xlsx`) is structured into 8 dedicated worksheets:

| Sheet Name | Description |
| :--- | :--- |
| `United States 10-Year Bond Yiel` | Benchmark historical 10Y U.S. Treasury yield data for $R_f$ calibration. |
| `stock price history` | Raw adjusted closing stock prices for 10 U.S. equities. |
| `stock price history 2` | Daily log return computations, daily summary statistics, and initial matrices. |
| `log returns` | Detailed log returns, market excess returns, CAPM Beta ($\beta$) calculations, and risk parameters. |
| `portfolio return simulation` | **Cholesky Matrix**, correlated random normal deviates, and Monte Carlo price path simulations. |
| `activity 2` | Random weight simulations, portfolio return/variance formulas, and Minimum Volatility Portfolio optimization. |
| `views` | Investor view definitions ($P$ and $Q$ matrices) and view uncertainty parameters. |
| `black litterman` | Market cap allocations, equilibrium returns ($\Pi$), posterior distributions, and Black–Litterman optimized portfolio weights. |

---

## 🚀 How to Use / Inspect the Model

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/black-litterman-portfolio-optimization.git](https://github.com/YOUR_USERNAME/black-litterman-portfolio-optimization.git)s
