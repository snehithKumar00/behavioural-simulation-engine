# Predictive Analytics for Player Retention

## Overview
This project is a full-stack predictive analytics tool designed for game developers. It utilizes **Agent-Based Modeling (ABM)**, **Monte Carlo simulations**, and **Unsupervised Machine Learning** to mathematically forecast player retention. Instead of reacting to real-world churn, developers can simulate 30 days of gameplay across thousands of unique virtual agents to proactively identify difficulty bottlenecks and discover player behavioral archetypes.

## Key Features
* **Agent-Based Modeling:** Simulates up to 2,000 unique virtual players, each assigned randomized statistical "DNA" (Skill, Patience, Learning Rate).
* **Monte Carlo Simulation:** Runs a 30-day temporal loop featuring daily probability rolls to determine dynamic flow-state (Frustration vs. Boredom) and churn events.
* **Unsupervised Machine Learning:** Utilizes **K-Means Clustering** to autonomously evaluate player telemetry and categorize users into human-readable industry personas (e.g., *Rage Quitters*, *Flow-State Masters*).
* **Headless Visual Analytics:** Generates complex Matplotlib graphs (Stacked Area Charts, Hexbin Density Maps) directly in the server's RAM and passes them to the frontend as lightweight Base64 strings.

## Technology Stack
* **Frontend:** HTML5, CSS3, Vanilla JavaScript (ES6+), Bootstrap 5 (Dark Mode UI)
* **Backend:** Python 3, Flask (RESTful API)
* **Mathematics & Simulation:** NumPy (Normal/Uniform Distributions, Array Math)
* **Machine Learning:** Scikit-Learn (K-Means, StandardScaler)
* **Data Visualization:** Matplotlib ('Agg' backend)

## Mathematical Models Used
1. **Normal & Uniform Distributions:** Used to generate heterogeneous agent populations, ensuring a realistic mix of player skill and patience thresholds.
2. **Logistic (Sigmoid) Function:** Acts as the endogenous churn trigger. Calculates the exact exponential probability of a player quitting based on their emotional threshold.
3. **Euclidean Distance:** The underlying metric used by the K-Means algorithm to measure the similarity between agents and cluster them into behavioral cohorts.

## Project Structure
* `app.py` - The main Flask server. Acts as the traffic controller, routing API requests, triggering the simulation, drawing Base64 graphs, and serving the frontend.
* `engine.py` - The core Monte Carlo loop. Spawns the agent population, manages the 30-day temporal loop, and tallies the final telemetry.
* `player.py` - The Object-Oriented blueprint for the virtual agents. Contains the flow-state logic that calculates daily frustration and boredom.
* `ml_analytics.py` - The machine learning pipeline. Scales the raw telemetry and runs K-Means clustering to generate player personas.
* `templates/index.html` - The frontend user interface and dashboard.

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [your-repo-link-here]
   cd [your-repo-name]
   ```

2. **Install the required Python dependencies:**
   Ensure you have Python 3 installed, then run:
   ```bash
   pip install flask numpy scikit-learn matplotlib
   ```

3. **Run the Flask Web Server:**
   ```bash
   python app.py
   ```
   *(Note: On some systems, you may need to use `python3 app.py`)*

4. **Access the Dashboard:**
   Open your web browser and navigate to:
   `http://127.0.0.1:5000` or `http://localhost:5000`

## Future Scope (Version 2.0)
* Integration of **Deep Reinforcement Learning (PPO)** to allow agents to autonomously discover gameplay exploits.
* Native plugin development for **Unreal Engine 5** and **Unity** to run predictive simulations directly inside the 3D editor viewport.

---
*Developed as a Computer Science Capstone Project.*