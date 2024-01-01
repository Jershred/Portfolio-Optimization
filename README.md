# Portfolio Optimization with Risk-Free Asset and Multiple Risky Assets

## Introduction
This notebook presents a framework for portfolio optimization that incorporates both a risk-free asset and multiple risky assets. The theory builds upon Modern Portfolio Theory (MPT), the Capital Market Line (CML), and the Capital Asset Pricing Model (CAPM).

---

## Assumptions
1. Markets are efficient.
2. Investors are rational and maximize utility.
3. A risk-free asset is available for borrowing and lending at a constant rate ($r_f$).
4. No transaction costs or taxes.
5. Asset returns are normally distributed (often relaxed).
6. Single-period investment horizon.

---

## Mathematical Formulation

### Risky Portfolio
The expected return $E[R_m]$ and risk $\sigma_m^2$ for a portfolio containing $n$ risky assets are:
$$
E[R_m] = \sum_{i=1}^{n} w_i E[R_i]
$$
$$
\sigma_m^2 = \sum_{i=1}^{n} \sum_{j=1}^{n} w_i w_j \rho_{ij} \sigma_i \sigma_j
$$

### Portfolio with Risk-Free Asset
The expected return $E[R_p]$ and risk $\sigma_p$ for the overall portfolio are:
$$
E[R_p] = w_f \cdot r_f + (1 - w_f) \cdot E[R_m]
$$
$$
\sigma_p = (1 - w_f) \cdot \sigma_m
$$

---

## Optimization Steps
1. **Risky Portfolio Optimization**: Identify the Tangency Portfolio that maximizes the Sharpe ratio:
$$
\text{Sharpe Ratio} = \frac{E[R_m] - r_f}{\sigma_m}
$$

2. **Capital Market Line (CML)**:
$$
E[R_p] = r_f + \left( \frac{E[R_m] - r_f}{\sigma_m} \right) \sigma_p
$$

3. **Asset Allocation**: Depending on the investor's risk tolerance, allocate between the risk-free asset and the Tangency Portfolio.
$$
w_f = 1 - \frac{\text{Investor's Risk Tolerance} \times (\text{Tangency Portfolio Excess Return})}{\text{Tangency Portfolio Risk}^2}
$$

---

## References
- Markowitz, H. (1952). "Portfolio Selection," The Journal of Finance, 7(1), 77-91.
- Sharpe, W.F. (1964). "Capital Asset Prices: A Theory of Market Equilibrium under Conditions of Risk," Journal of Finance, 19(3), 425-442.
- Luenberger, D.G. (1998). "Investment Science," Oxford University Press.

---

## Bias Consideration
The model assumes past statistics are indicative of future performance, which may not always be the case.
