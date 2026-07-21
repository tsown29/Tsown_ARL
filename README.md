# Tsown_ARL
# 🚗 2D Autonomous Lane Following via Tabular Q-Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Reinforcement Learning](https://img.shields.io/badge/RL-Tabular%20Q--Learning-green.svg)
![IEEE Standard](https://img.shields.io/badge/Paper-IEEE%20Format-orange.svg)
![License](https://img.shields.io/badge/License-MIT-brightgreen.svg)

A lightweight, 2D simulation framework for autonomous Lane Keeping Systems (LKS) using Tabular Q-Learning. This repository contains the complete implementation, environment mechanics, and training evaluation scripts for testing reinforcement learning agents on straight and sinusoidal road tracks.

---

## 📌 Features

* **Custom 2D Road Environment:** Built with a continuous coordinate system ($1000 \times 400$ px) featuring dynamic parametric track generation (Straight & Sinusoidal curves).
* **Tabular Q-Learning Implementation:** Discrete state-space binning combined with an $\epsilon$-greedy exploration strategy decaying exponentially.
* **Reward Shaping Engine:** Piece-wise continuous reward distribution penalizing lateral deviation and rewarding survival/goal-reaching actions.
* **Academic Paper Included:** Includes the full LaTeX source code compiled according to the IEEE conference format.

---

## ⚙️ System Architecture & MDP Formulation

The lane-following problem is framed as a Markov Decision Process (MDP):

* **State Space ($\mathcal{S}$):** Continuous lateral deviation $d_t = y_t - y_{\text{target}}(x_t)$ bounded in $[-40, 40]$ pixels and discretized into 10 distinct state bins ($s_t \in \{0, 1, \dots, 9\}$).
* **Action Space ($\mathcal{A}$):** Discrete lateral steering commands:
  * `0`: Move Up / Shift Left ($\Delta y = -2$ px)
  * `1`: Hold Position ($\Delta y = 0$ px)
  * `2`: Move Down / Shift Right ($\Delta y = +2$ px)
* **Reward Function ($\mathcal{R}$):**
  $$r_t = \begin{cases} -100 & \text{if Off-road Crash (Terminal)} \\ +200 & \text{if Goal Reached (Terminal)} \\ 10 - \lfloor \frac{\vert{}d_t\vert{}}{4.0} \rfloor + 1 & \text{otherwise} \end{cases}$$

---

## 🚀 Getting Started

### Prerequisites

Make sure you have Python installed on your system. Install the required dependencies using:

```bash
pip install numpy matplotlib pygame
