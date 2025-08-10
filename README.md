# Assignment 3 – Q-Learning for Pathfinding

## 📄 Summary

This assignment focuses on implementing and analyzing **Q-Learning** for pathfinding in a grid-based environment. The agent navigates from a start cell to a goal cell, while optionally avoiding traps and collecting boosts. The work involves training agents under different reward settings and comparing results with **Breadth-First Search (BFS)** solutions.

---

### **Part 1 – Q-Learning Implementation**

- Implemented **Q-Learning** in the provided `QL Assignment.ipynb` framework.
- Generated a unique grid maze based on the SR number.
- Used **BFS** to verify that a path exists from start to goal.
- Applied an **ε-greedy policy** for exploration-exploitation tradeoff.
- Trained the agent in two configurations:
  1. **Traps & Boosts Disabled** – Learned the shortest path, matching BFS output.
  2. **Traps & Boosts Enabled** – Learned to maximize rewards while avoiding penalties.
- Saved trained Q-tables (`.pkl`) for both cases.

---

### **Part 2 – Reward Configuration Analysis**

- Experimented with different reward values for traps, boosts, and step costs.
- Compared path strategies, step counts, and detours.
- Found that:
  - **High trap penalties** increased avoidance behavior.
  - **High boost rewards** encouraged detours to collect boosts.

---

### **Part 3 – Manual Q-Value Updates**

- Disabled traps and boosts for this analysis.
- Trained an agent and generated its Q-table.
- Simulated the **first 5 steps** of an episode manually:
  - Chose actions using the ε-greedy policy.
  - Updated Q-values using the **Bellman update rule**:
    \[
    Q(s,a) \leftarrow Q(s,a) + \alpha [r + \gamma \max_{a'} Q(s',a') - Q(s,a)]
    \]
  - Verified manual results against automated training updates.

---

### **📊 Key Results & Observations**

- **Traps/Boost Disabled** → Shortest paths identical to BFS.
- **Traps/Boost Enabled** → Learned to avoid traps and seek boosts, sometimes taking longer routes.
- **Reward Tweaks** → Clear tradeoff between path length and reward maximization.
- **Manual Updates** → Hand-calculated Q-values aligned with expected learning patterns.

---

### **🛠 Tools & Libraries Used**

- **Python 3**
- `numpy`
- `pickle`
- `matplotlib`
- BFS utility (`BFS.ipynb`) for path validation
- Custom Q-Learning environment (`QL Assignment.ipynb`)
