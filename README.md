# 🏥 Emergent Dynamics of Hospital Patient Flow

### A Complexity Science Approach to Criticality, Avalanches, and System Collapse

---

## 📌 Overview

This project models **hospital patient flow** as a **complex adaptive system** using simulation.
It investigates how **stochastic demand, limited capacity, and local decision-making** interact to produce system-wide behavior such as:

* Stable operation
* Congestion
* Avalanche-like events
* System collapse

The study demonstrates how **global system behavior emerges from simple local rules**, a key concept in complexity science.

---

## 🎯 Objectives

* Model patient flow using **queue + bed occupancy dynamics**
* Incorporate:

  * **Noise** (random arrivals)
  * **Connectivity** (flow between system components)
  * **Behavioral effects** (inefficiency in discharge)
* Analyze **avalanche events** in queue dynamics
* Study **phase transition**:

  * Stable → Critical → Collapse

---

## ⚙️ Model Description

The system consists of:

* **Queue (Emergency Department)** → incoming patients
* **Beds (Hospital Capacity)** → admitted patients
* **Discharge Process** → exit from system

### Key Variables

* `Q(t)` → Queue size
* `O(t)` → Bed occupancy
* `B` → Total beds

---

## 🔁 Simulation Logic

At each time step:

1. **Arrival**

   * Patients arrive via Poisson process:

     ```
     A(t) ~ Poisson(λ)
     ```

2. **Admission**

   * Based on available beds:

     ```
     Admit = min(Q, B - O)
     ```

3. **Discharge**

   * Influenced by:

     * Base rate
     * Behavioral inefficiency (α)
     * Congestion feedback (β)

4. **Avalanche Detection**

   ```
   s(t) = Q(t) - Q(t-1)
   ```

---

## 🧪 Scenarios Simulated

| Case | λ (Load) | α (Behavior) | Description          |
| ---- | -------- | ------------ | -------------------- |
| 1    | 3        | 0            | Stable system        |
| 2    | 3        | 0.2          | Local inefficiency   |
| 3    | 5        | 0            | Near-critical regime |
| 4    | 6        | 0.2          | System collapse      |

---

## 📊 Results Summary

### 🔹 Low Load (λ = 3)

* System remains stable
* Minimal queue
* No avalanches

### 🔹 With Behavioral Inefficiency

* Small spikes appear
* Local instability

### 🔹 Moderate Load (λ = 5)

* Large fluctuations
* Avalanche emergence
* Near-critical behavior

### 🔹 High Load (λ = 6)

* Bed saturation
* Queue grows indefinitely
* System collapse

---

## 🌊 Avalanche Analysis

* Avalanches represent **sudden congestion events**
* Behavior observed:

  * No avalanches → stable regime
  * Small avalanches → local disturbances
  * Large avalanches → cascade behavior

---

## 🧠 Key Insights

* System behavior depends on **load vs capacity**
* Behavioral inefficiency **amplifies instability**
* Collapse emerges from:

  * feedback loops
  * connectivity
  * demand pressure

---

## 🔬 Complexity Science Concepts Used

* Complex Adaptive Systems
* Nonlinearity
* Emergence
* Feedback loops
* Self-Organized Criticality (qualitative)

---

## 📁 Repository Structure

```
├── code/
│   ├── simulation.py
│
├── results/
│   ├── queue_plots/
│   ├── occupancy_plots/
│   ├── avalanche_plots/
│
├── report/
│   ├── report.tex
│   ├── report.pdf
│
└── README.md
```

---

## 🚀 How to Run

1. Install dependencies:

```
pip install numpy matplotlib
```

2. Run simulation:

```
python simulation.py
```

3. Outputs:

* Queue plots
* Occupancy plots
* Avalanche distributions

---

## 📚 Reference

Wright, M. (2024).
*A need for systems thinking and the appliance of (complexity) science in healthcare*.
Future Healthcare Journal.

---

## 🙏 Acknowledgment

* Course: **Complexity Science in Chemical Industry (CLL798)**
* Instructor: **Rajesh Khanna**
* AI assistance used for modeling, coding, and documentation

---

## 📌 Note

This project is developed for academic purposes to demonstrate **complexity science concepts through simulation**.

---

## ⭐ If you found this useful

Give a ⭐ to the repo!
