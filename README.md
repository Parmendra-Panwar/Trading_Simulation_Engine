# **Deterministic Trading Engine & Backtesting Simulator (C++)**


## Project Overview
>
> This project implements a deterministic, event-driven trading engine in C++ that simulates how real exchanges process orders.
>
> The same core engine is used to replay historical market data for backtesting, ensuring consistent and reproducible results.
>
---

## Project Objectives

The system models a real exchange by processing market data and orders through a single-threaded, event-driven core.
It includes a price-time priority order book, a matching engine for handling partial and full fills, and a pre-trade risk layer to reject invalid orders.
Historical market data can be replayed to simulate trading activity exactly as it would occur in real time.
The engine guarantees deterministic behavior, meaning identical inputs always produce identical outputs.
This design enables reliable backtesting, auditability, and clear separation between trading logic and execution infrastructure.

---

## ⚠ Disclaimer

This project is strictly for **learning, research, and engineering practice**.
It should not be used for real trading decisions.

---