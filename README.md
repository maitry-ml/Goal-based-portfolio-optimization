# Goal-Based Portfolio Optimization

A simulation-driven portfolio optimization project that applies **Monte Carlo methods**, **brute-force search**, and **continuous optimization** to maximize the probability of achieving long-term financial goals.

---

## Project Overview

This repository contains the implementation of **Assignment V: Goal-Based Portfolio Optimisation** as part of course DS6701 DSAI in Fiance, at IITM, focused on designing a **static investment portfolio** for a 20-year horizon.

The objective is to determine the portfolio allocation that maximizes the likelihood of achieving a **₹1.5 Crore retirement target**, while accounting for:

* annual savings growth,
* intermediate financial goals,
* borrowing penalties for shortfalls,
* and uncertainty in market returns.

The project compares two different goal sequences to study how objective timing changes optimal portfolio composition.

---

## Financial Framework

* **Time Horizon:** 20 years
* **Initial Monthly Savings:** ₹20,000
* **Savings Growth Rate:** 4% annually
* **Borrowing Cost:** 12% annual interest
* **Terminal Retirement Goal:** ₹1.5 Crores

---

## Portfolio Universe

The analysis uses five Indian equities:

* Tata Consultancy Services
* HDFC Bank
* Reliance Industries
* Sun Pharmaceutical
* ITC Limited

Historical daily price data was collected from January 2014 to December 2023 using the yfinance library.

---

## Methodology

### 1. Statistical Estimation

Using historical data:

* Annualized expected returns were computed
* Annualized risk (standard deviation) was calculated
* Covariance matrix was derived for portfolio construction

---

### 2. Discrete Portfolio Optimization

Generated all valid portfolio combinations using discrete weights:

```text
{0, 0.25, 0.5, 0.75, 1.0}
```

Subject to:

```text
Sum of weights = 1.0
```

This resulted in **70 valid portfolios**.

---

### 3. Monte Carlo Simulation

For each portfolio:

* 5,000 simulation paths
* 20-year investment horizon
* yearly stochastic returns
* intermediate goal deductions
* borrowing if wealth is insufficient

Success probability is defined as the proportion of simulations where the retirement goal is achieved with no debt remaining.

---

### 4. Bonus Optimization

Implemented **Differential Evolution** for continuous portfolio weights:

* unrestricted real-valued allocations
* short-selling allowed
* global optimization search
* objective: maximize success probability

---

## Results Summary

| Scenario   | Optimization Type | Success Probability |
| ---------- | ----------------- | ------------------: |
| Sequence A | Discrete          |               5.46% |
| Sequence B | Discrete          |              88.40% |
| Sequence A | Continuous        |               6.44% |
| Sequence B | Continuous        |              61.04% |

---

## Key Insight

Early financial goals force aggressive portfolio allocations with higher risk, while delayed goals allow compounding to improve long-term success.

This demonstrates that **goal timing is as important as portfolio design** in wealth planning.





## Technologies Used

* Python
* NumPy
* Pandas
* yfinance
* SciPy
* Monte Carlo Simulation
* Differential Evolution

---

## Conclusion

This project highlights the importance of aligning investment strategies with financial objectives. While static portfolios simplify decision-making, goal structures and withdrawal timing significantly affect long-term outcomes.

The findings reinforce the principles of **goal-based investing under uncertainty**.

---
