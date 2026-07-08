# Interest Rate Derivatives Valuation Engine

## Project Overview

This project is a **valuation engine for interest rate derivatives**, focused on the **valuation application layer** within a financial system. It loads pre‑constructed zero‑coupon yield curves, interpolates yields for arbitrary tenors, derives discount factors, and computes the present value (PV) of cash flows.

It serves as a **minimalist prototype** of the PV Engine found in major banks' market risk systems (e.g., FRTB compliance).

---

## Core Features

###`yield_curve.py` — Main Valuation Class
The `YieldCurve` class provides end‑to‑end valuation capabilities:

- **Data Ingestion**: Reads zero‑coupon curve data from a JSON file (tenor, yield, base date) and automatically rolls curve dates to the current trading day.
- **Tenor Interpolation**: Implements **linear interpolation** to estimate yields for non‑standard tenors (e.g., 3.5Y) between standard nodes (e.g., 1Y, 2Y, 5Y, … 30Y).
- **Discount Factor Derivation**: Converts interpolated yields into discount factors.
- **PV & Profit/Loss Calculation**: Computes the present value of single or multiple cash flows, and generates visualisations of profit curves and average daily profit across different tenors.
