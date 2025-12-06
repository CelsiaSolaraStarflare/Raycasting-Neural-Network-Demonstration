Raycasting Neuroevolution Cars

A fully in-browser simulation of self-driving cars using raycasting, genetic algorithms, and a tiny neural network, all running in pure HTML + JavaScript.

This project visualizes how simple agents learn to navigate a track using simulated distance sensors and evolutionary selection—no external libraries needed.

🚗 Features
🌐 Pure HTML/JS Implementation

No frameworks required.

Just open raycasting.html in a browser and it runs instantly.

🧠 Tiny Neural Network

Each car has:

7 distance sensors (raycasts)

8 hidden neurons

2 outputs (left-steer, right-steer)

All networks mutate during evolution. No backpropagation—only neuroevolution.

🔬 Evolutionary Training (Genetic Algorithm)

Population: 500 cars per generation

Selection: Top performers become parents

Mutation: Slight random changes to weights

Goal: Survive as long as possible without crashing

The best model each generation is automatically kept and used to spawn children.

🎯 Visual Raycasting

Cars shoot rays outward to detect walls.
Color-coded:

Red → very close to wall

Yellow → moderate distance

No line → no obstacle detected in range

🚀 Speed Control

Adjust training speed from 1x to 300x using the slider.
This makes evolution way faster while still letting you watch the progress.

🏁 Custom Race Track

A hand-crafted flowing S-shaped track with:

Outer boundaries

Inner boundaries

Midline glow

Starting line

Rendered directly with Canvas 2D API.

🧩 How It Works
1. Raycasting Sensors

Each car shoots 7 rays in a spread (≈ 162°) and receives values from 0 to 1 based on collision distance.

2. Neural Network Forward Pass

Inputs → 8 hidden neurons → 2 outputs
Outputs determine steering direction:

Output[1] – Output[0] → steering force

3. Movement & Collisions

The car moves forward at constant speed and rotates via its NN output.
If its polygon intersects any border → crash.

4. Fitness

Cars score fitness based on distance traveled.

5. Generation Cycle

When all cars crash:

Sort by fitness

Keep top ~10% as parents

Clone + mutate into next generation

Display best fitness & generation count

🖼️ UI Overview

The top stats show:

Generation

Alive Cars

Best Fitness Ever Achieved

Simulation Speed

The lead car highlights:

A bright cyan body

Sensor rays

All other cars are drawn in faint cyan.

▶️ How to Run

Just open:

raycasting.html


in any modern browser (Chrome recommended).

No server needed. No build steps.

🔧 Project Structure

Everything is contained inside one HTML file:

raycasting.html
│
├─ Canvas rendering
├─ Track builder
├─ Car physics + collision polygons
├─ Raycasting logic
├─ Neural network (forward pass + mutation)
├─ Genetic algorithm
└─ UI handling

📚 Future Extensions (Optional Ideas)

If you wanna expand:

Add speed acceleration/braking

Add multi-lap fitness

Save/load best brain to localStorage

Add obstacles or traffic

Add drift physics

Visualize the NN weights in real-time

Tell me if you want any of these implemented and I’ll code them with you 💞.

❤️ Credits

Created fully in vanilla HTML5 Canvas + JavaScript as an educational and experimental simulation for neuroevolution.
