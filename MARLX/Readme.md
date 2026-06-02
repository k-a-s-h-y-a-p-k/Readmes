<div align="center">

# MARL for Market Simulation

### Multi-Agent Reinforcement Learning for Market Simulation and Automated Exploit Discovery

A crash-test facility for financial protocols. Hundreds of self-learning trading agents are released into a simulated market and, acting only to maximize their own profit, autonomously discover the economic exploits that would otherwise surface only after a protocol launches with real money.

<br/>

[![Status](https://img.shields.io/badge/status-in%20development-f59e0b?style=flat-square)](#roadmap)
[![Domain](https://img.shields.io/badge/domain-Deep%20AI%20%C2%B7%20Web3%20%C2%B7%20FinTech-6366f1?style=flat-square)](#problem-statement)


<br/>

**[Overview](#overview)** · **[Problem Statement](#problem-statement)** · **[Concepts](#core-concepts)**

</div>


## Overview

This project builds a high-fidelity simulator of a DeFi-style financial market and populates it with hundreds of independent reinforcement-learning agents. Each agent is given a single objective — **maximize its own profit** — and is never told *how* to achieve it.

Because the agents act selfishly and concurrently, they learn, on their own, to discover ways to break or exploit the market: price manipulation, cascading liquidations, flash-loan attacks, and oracle manipulation. These are strategies no human auditor explicitly scripted.

The objective:

> Surface these exploits inside a safe simulation **before** a real protocol launches with real money.

| Aspect | Summary |
|---|---|
| **What it is** | A market simulator paired with a swarm of self-learning RL agents |
| **What it does** | Automatically discovers economic exploits and systemic risks |
| **Who it serves** | Web3 protocol designers, DeFi teams, and quantitative risk desks |
| **Core technique** | Multi-Agent Reinforcement Learning (MARL) with PPO / MAPPO |
| **Flagship demo** | Simulate ten years of aggressive adversarial trading in an afternoon |

---

## Problem Statement

Financial markets — and decentralized exchanges in particular — are **complex adaptive systems**. A protocol may be mathematically sound on paper, yet behave unpredictably once thousands of strategic actors interact within it.

Traditional testing catches **bugs**. It does not catch **emergent economic exploits**, because those only appear when many strategic agents collide.

```
                    A protocol "proven correct on paper"
                                       |
            +--------------------------+--------------------------+
            v                                                     v
   Unit tests pass                          Thousands of profit-seeking agents interact
   Audit signed off                                       |
   Formal proof holds                                     v
            |                                    Flash-loan drain
            |                                    Liquidation cascade
            v                                    Oracle manipulation
       "Ship it."  <----------------------------  Value extracted
```

Real DeFi exploits have resulted in losses measured in billions. Protocol teams pay for manual audits that take weeks and still miss economic attacks. The core insight of this project:

> Instead of relying on humans to imagine every possible attack, let AI agents discover them automatically by playing the market millions of times.

### What the brief requires

The deep research component must:

1. Build a **high-fidelity, highly concurrent simulation environment** of a financial protocol.
2. Populate it with **hundreds of independent RL agents**, each with **slightly different reward functions** (market makers, arbitrageurs, aggressive attackers, and others).
3. Run them through **millions of generations** of training.
4. **Automatically discover complex, multi-step systemic exploits** before the protocol launches.

### Venture potential

An automated stress-testing platform for quantitative desks and Web3 protocols. The proposition: *upload your protocol's rules, and receive a ranked list of discovered exploits, complete with reproduction steps, after a simulation of years of adversarial market behavior.*

---

## Core Concepts


<details>
<summary><b>Reinforcement Learning (RL)</b></summary>

Learning by trial and error to maximize a reward signal. The loop: an agent observes a state, selects an action, the environment changes and returns a reward, and the agent updates its policy — repeated many times.

Key terms: **State** (what the agent observes), **Action** (what it can do), **Reward** (the good/bad signal), **Policy** (its strategy, a neural network), **Episode** (one full run).
</details>

<details>
<summary><b>Multi-Agent RL (MARL)</b></summary>

Many agents learning in the same world simultaneously. This is substantially harder because the environment is **non-stationary**: from any single agent's perspective, the world keeps changing as other agents also learn. The market effectively *is* the other agents, and the resulting arms race is what surfaces realistic exploits.
</details>

<details>
<summary><b>PPO and MAPPO</b></summary>

**Proximal Policy Optimization** is a policy-gradient method that takes small, conservative steps so a single bad batch cannot derail a good policy. This stability is why it is the industry default. **MAPPO** is PPO adapted to multi-agent settings, often with a shared critic. The project uses established libraries rather than implementing PPO from scratch.
</details>

<details>
<summary><b>Automated Market Maker (x*y=k)</b></summary>

Most DeFi exchanges have no order book. A liquidity pool holds two assets and a formula sets the price. The classic **constant-product** rule requires that, for a pool holding `x` of token A and `y` of token B, the product `x * y = k` stays constant. Buying token A automatically raises its price. The formula is simple to implement and is where many DeFi exploits originate.
</details>

<details>
<summary><b>The exploits under investigation</b></summary>

- **Flash-loan attack** — borrow a large sum uncollateralized, manipulate a price, take profit, and repay, all within a single atomic transaction.
- **Cascading liquidations** — a sell-off drops a price, forcing liquidations, which dump more assets and drive the price lower, in a self-reinforcing collapse.
- **Oracle manipulation** — distorting the external price feed a protocol relies on.
- **Sandwich and front-running attacks** — exploiting the order in which trades are processed.
</details>

---

## About

Developed at **PESU Venture Labs** as a Deep AI, Web3, and FinTech research project. The guiding thesis:

> Artificial intelligence here is not about prediction. It is about simulating a complex, multi-actor ecosystem and studying the behavior that emerges.

**Domain:** Deep AI, Web3/Crypto, FinTech.
**Core concepts:** Multi-Agent Reinforcement Learning, game theory (Nash equilibria), concurrent system simulation, Proximal Policy Optimization.

---

**Developed by** 
  Ram Ganesh V · Kashyap K · Nithya Sri P.B · Neema Shrivastava

</div>
