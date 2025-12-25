# **Modular Trading Strategy Simulation & Backtesting Engine (C++)**


## Project Overview
>
> This project is a **modular trading strategy simulation and backtesting engine** written in **C++**.
>
> To convert discretionary trading ideas into **deterministic, testable, and reproducible rule-based systems**, and to evaluate them on historical market data.
>
---

## Project Objectives

* Design a **clean, modular architecture** for trading strategy research
* Support **historical backtesting - fast backtesting** on data (1m–1H)
* Allow **independent strategy modules** to be developed and tested in isolation
* Ensure **deterministic results** (same input → same output)
* Keep the system **lightweight, fast, and memory-efficient**
* Build something that can **grow over time**, not a one-off script

---

## What This Project Is NOT (Important for Interviews)

* ❌ Not a profitable trading guarantee
* ❌ Not connected to real brokers
* ❌ Not high-frequency trading

This project focuses on **software design, data handling, and simulation correctness**.

---

## 📂 Market Data Handling

* Input format: **CSV (OHLCV)**
* Supported timeframes:

  * 1 minute
  * 5 minute
  * 15 minute
  * 1 hour
* Data window:

  * Only **1–3 months loaded per run**
  * Prevents unnecessary memory usage
* Data is processed **sequentially (candle by candle)** to avoid look-ahead bias

Example CSV format:

```
Date;Open;High;Low;Close;Volume
2024.12.30 21:30;2604.37;2607.16;2604.12;2607.03;575
```

---

## Strategy Philosophy

Instead of hardcoding one strategy, the system is designed around **strategy composition**.

Each strategy is built using **independent components**, such as:

* Swing High / Swing Low structure
* Volume filters
* Volatility filters
* Liquidity-Based Levels
* Fibonacci-based zones
* Optional indicator confirmations

Each component can be:

* Enabled / disabled
* Tuned per timeframe
* Tested independently

This allows **experimentation without rewriting the engine**.

---

## 🧩 Planned Core Modules (Incremental)

This is a **module-based project**, developed step by step.

### 1️⃣ Market Data Module

* CSV parsing
* Candle validation
* Timeframe abstraction
* Sequential candle access

**Status**: Planned / Initial development

---

### 2️⃣ Swing Structure Module

* Swing high / low detection
* Configurable sensitivity
* No future data leakage

**Status**: Planned (first strategy focus)

---

### 3️⃣ Level Generation Module

* Levels derived from swing structure
* Stored and reused during simulation
* Updated only at fixed intervals (timeframe-based)

**Status**: Planned

---

### 4️⃣ Strategy Interface

* Common interface for all strategies
* Allows plugging different logic into backtest engine
* Supports decorator-style composition

**Status**: Planned

---

### 5️⃣ Backtesting Engine

* Candle-by-candle simulation
* Trade entry & exit simulation
* Exact PnL calculation
* No randomness, no approximation

**Status**: Planned

---

### 6️⃣ Stop-Loss & Target Trailing Module

* Data-driven SL & target levels
* Multiple trailing stages
* No hardcoded “1/3 or 1/2” rules
* Levels derived from historical structure

**Status**: Planned

---

### 7️⃣ Future phase

* Console-Based Live Simulation
* Uses free market data APIs
* Periodic level recalculation
* Buy/Sell/SL/Target logs printed to console
* No broker integration
* Additional strategy modules
* Improved volatility regime detection
* Multi-strategy comparison
* Performance profiling

**Status**: Future phase

---

## ⏱ Backtesting Principles

* Deterministic execution
* No look-ahead bias
* Single-pass simulation
* Same strategy + same data → **exact same result every run**

This makes results **comparable and debuggable**.

---

## 🛠 Technology Stack

* **Language**: C++17
* **Build System**: CMake
* **Data**: CSV files
* **Design Patterns**:

  * Strategy
  * Decorator
  * Factory
* **Tools**:

  * Git / GitHub
  * VS Code
  * Optional Python (only for result visualization)

---

## Development Phases 

### Phase 1: Foundation

* CSV parser
* Candle validation
* Timeframe handling

**Deliverable**: Clean, validated market data in memory

---

### Phase 2: Core Structure

* Swing High / Low detection
* Configurable sensitivity
* Level creation & storage

**Deliverable**: Levels generated from historical data

---

### Phase 3: Backtesting Core

* Strategy-agnostic backtesting engine
* Trade simulation (buy/sell)
* PnL calculation

**Deliverable**: Backtest runs with dummy strategy

---

### Phase 4: Risk Management

* Stop-loss logic
* Target logic
* Multi-level SL & target trailing (data-driven)

**Deliverable**: SL/Target trailing verified in backtest

---

### Phase 5: Strategy Integration

* Integrate swing + volume strategy
* Decorator-based composition

**Deliverable**: First complete strategy backtested

---

## ⚠ Disclaimer

This project is strictly for **learning, research, and engineering practice**.
It should not be used for real trading decisions.

---
* Help you explain this project in **2-minute interview pitch**

Just say the word.
