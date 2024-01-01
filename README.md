# Portfolio Optimization with Risk-Free Asset and Multiple Risky Assets

## Introduction
This repository hosts a Jupyter notebook that provides a comprehensive approach to portfolio optimization, integrating a risk-free asset with several risky assets. It is grounded in key financial theories, including Modern Portfolio Theory (MPT), the Capital Market Line (CML), and the Capital Asset Pricing Model (CAPM).

---

## Assumptions
1. Markets function efficiently.
2. Investors behave rationally, aiming to maximize their utility.
3. Availability of a risk-free asset, offering a constant return rate (\(r_f\)) for both borrowing and lending.
4. Absence of transaction costs and taxes.
5. Normal distribution of asset returns, although this is a flexible assumption.
6. Investment strategy focuses on a single-period horizon.

---

## Mathematical Framework

### Risky Portfolio
For a portfolio with \(n\) risky assets, the expected return \(E[R_m]\) and risk \(\sigma_m^2\) are given by:
\[
E[R_m] = \sum_{i=1}^{n} w_i E[R_i]
\]
\[
\sigma_m^2 = \sum_{i=1}^{n} \sum_{j=1}^{n} w_i w_j \rho_{ij} \sigma_i \sigma_j
\]

### Portfolio Including Risk-Free Asset
The portfolio's overall expected return \(E[R_p]\) and risk \(\sigma_p\) are calculated as:
\[
E[R_p] = w_f \cdot r_f + (1 - w_f) \cdot E[R_m]
\]
\[
\sigma_p = (1 - w_f) \cdot \sigma_m
\]

---

## Optimization Procedure
1. **Optimizing Risky Portfolio**: Identify the Tangency Portfolio, which maximizes the Sharpe ratio:
\[
\text{Sharpe Ratio} = \frac{E[R_m] - r_f}{\sigma_m}
\]

2. **Establishing the Capital Market Line (CML)**:
\[
E[R_p] = r_f + \left( \frac{E[R_m] - r_f}{\sigma_m} \right) \sigma_p
\]

3. **Asset Allocation Strategy**: Based on the investor's risk preference, allocate between the risk-free asset and the Tangency Portfolio.
\[
w_f = 1 - \frac{\text{Investor's Risk Tolerance} \times (\text{Tangency Portfolio Excess Return})}{\text{Tangency Portfolio Risk}^2}
\]

---

## References
- Markowitz, H. (1952). "Portfolio Selection," The Journal of Finance, 7(1), 77-91.
- Sharpe, W.F. (1964). "Capital Asset Prices: A Theory of Market Equilibrium under Conditions of Risk," Journal of Finance, 19(3), 425-442.
- Luenberger, D.G. (1998). "Investment Science," Oxford University Press.

---

## Bias Consideration
This model is based on the premise that historical statistics are reflective of future trends, which may not always hold true.
