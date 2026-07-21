# 🚗 2D Autonomous Lane Following via Tabular Q-Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg) ![RL](https://img.shields.io/badge/RL-Q--Learning-green.svg) ![Paper](https://img.shields.io/badge/Paper-IEEE-orange.svg)

A lightweight 2D simulation framework for autonomous Lane Keeping Systems (LKS) using Tabular Q-Learning on straight and sinusoidal road tracks.

## 📌 Features
* **Custom 2D Environment:** $1000 \times 400$ px coordinate grid with continuous road curves (Straight & Sinusoidal).
* **MDP Formulation:** Continuous lateral tracking error discretized into 10 state bins; 3 steering actions ($\Delta y = \{-2, 0, +2\}$ px).
* **Performance:** Achieves 100% mission completion rate on both flat and dynamic curved tracks.
* **Academic Paper:** Includes full LaTeX paper formatted according to IEEE standards.

## 🚀 Quick Start
1. **Install Dependencies:**
   ```bash
   pip install numpy matplotlib pygame
