# Raycasting Neuroevolution Cars

A browser-based simulation demonstrating how simple agents can learn to drive using raycasting sensors and neuroevolution. Everything runs inside a single HTML file using only the HTML5 Canvas and vanilla JavaScript.

Copyright © Celsia Juilyn Fan.

---

## 🚗 Overview

This project simulates a population of cars navigating a custom track. Each car uses:

* **Raycasting sensors** to detect track boundaries
* A small **neural network** for decision‑making
* **Genetic algorithms** for improvement over generations

Cars drive forward at a constant speed and can only steer left or right. They crash when their polygon intersects the track borders. When all cars in a generation crash, a new generation is produced from the best-performing ones.

---

## ✨ Features

### Pure JS & HTML

* No libraries or dependencies
* Runs instantly in any modern browser

### Neural Network

* Inputs: 7 ray distances
* Hidden Layer: 8 neurons
* Outputs: steering signals
* Activation: Sigmoid
* Mutations applied to weights every generation

### Genetic Algorithm

* Population size: 500
* Top ~10% chosen as parents
* Best genome is preserved
* Children are mutated clones of parents

### Visual Components

* Sensors colored based on distance
* Leader car and its sensors highlighted
* Beautiful custom S‑shaped track with inner/outer loops
* Real-time stats: Generation, Alive, Best Fitness, Speed
* Slider for 1×–300× simulation speed

---

## 🎮 How It Works

### Raycasting

Each car emits evenly distributed rays. The distance to the nearest border becomes the neural network input.

### Decision Making

The neural network outputs two values. Their difference determines steering direction.

### Movement

Cars move forward automatically and adjust their angle based on NN output.

### Fitness

Each frame the car survives without crashing, its fitness increases.

### Evolution

Once all cars crash:

1. Sort by fitness
2. Select top performers
3. Clone brains
4. Apply weight mutations
5. Start new generation

---

## ▶️ Running the Project

Just open the `raycasting.html` file in any browser. No local server needed.

---

## 📁 File Structure

The entire demo is self-contained:

```
raycasting.html
  ├─ Canvas drawing
  ├─ Track geometry
  ├─ Neuroevolution logic
  ├─ Neural network class
  ├─ Car physics & collision
  └─ UI & speed controls
```

---

## 🌱 Ideas for Future Improvement

* Adjustable mutation rates
* Save/load trained networks
* Obstacles or traffic opponents
* Multi-lap fitness scoring
* Replay mode for best cars

---

## 📜 License

This is a open-sourced project that is free to use, modify, and learn from.
