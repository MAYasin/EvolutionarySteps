# 🏃 EvolutionarySteps

An AI-powered simulation where stickman agents learn to navigate 2D environments using **Neural Networks** and **Genetic Algorithms** within a physics-based sandbox.

---

## 🌟 Overview

This project explores reinforcement learning through evolution. Instead of being programmed with specific walking frames, these agents start with random movements. Through a process of natural selection, they evolve optimal walking strategies by interacting with a **Matter.js** physics engine.

### Key Features

* **Physics-Driven Movement**: Uses Matter.js for realistic ragdoll constraints and joint dynamics.
* **Neuroevolution**: Agents are controlled by a custom JavaScript Neural Network.
* **Genetic Algorithm**: Implements selection, crossover, and mutation to evolve behaviors over generations.
* **Real-time Visualization**: Built with p5.js to watch the learning process in your browser.
* **Data Persistence**: Export and import trained models (`Model.json`) to skip the training phase.

---

## 🛠️ Technical Stack

| Component | Technology | Role |
| --- | --- | --- |
| **Rendering** | [p5.js](https://p5js.org/) | Canvas visualization and animation loop |
| **Physics** | [Matter.js](https://brm.io/matter-js/) | Ragdoll constraints, gravity, and collisions |
| **Logic** | JavaScript (ES6+) | Neural network architecture and Genetic Algorithm |
| **Backend** | Node.js / Express | Local development server |

---

## 🧬 How It Works

The learning cycle follows a classic **Neuroevolution** loop:

1. **Initialization**: 50–100 stickmen are created with randomized neural weights.
2. **Simulation**: The Neural Network takes inputs (joint positions, body angle, velocity) and outputs torques for the limbs.
3. **Evaluation**: At the end of a "generation," each agent is assigned a **Fitness Score** based on the distance traveled and stability.
4. **Selection & Mutation**: The top performers are cloned into the next generation with small, random "mutations" in their neural weights.
5. **Iteration**: Over dozens of generations, coordinated walking patterns emerge from the chaos.

---

## 📂 Project Structure

```text
├── src/
│   ├── neuralnetwork.js   # The "brain" of the agents
│   ├── ragdoll.js         # Skeleton structure and joint constraints
│   ├── sketch.js          # p5.js simulation controller
│   ├── boundary.js        # Environment collision boxes
│   └── assets/            # Pre-trained Model.json files
├── docs/                  # Detailed logs and CSV performance metrics
├── server.js              # Express server config
└── package.json           # Scripts and dependencies

```

---

## 🚀 Getting Started

### Prerequisites

* [Node.js](https://nodejs.org/) (v14 or higher)
* npm (included with Node)

### Installation

1. **Clone the repo**

```bash
git clone https://github.com/MAYasin/Self-Learning-Stickman.git
cd Self-Learning-Stickman
```

2. **Install dependencies**

```bash
npm install
```

### Running the Project

* **Development**: `npm run dev` (Runs with hot-reloading)
* **Production**: `npm start` (Runs the Express server at `http://localhost:3000`)

---

## 📈 Training Insights

The `docs/` folder contains specific test cases:

* **Walking/**: Focused on horizontal displacement.
* **Physics Exploit/**: Agents finding "glitches" or unique ways to move that maximize fitness without traditional walking.

> **Note:** You can load any `Model.json` from these folders directly into the simulation to see the results of long training sessions.
