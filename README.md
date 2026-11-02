<div align="center">

# GENESIS (Architectural Overview)

**Genetic Engine for Neural Evolution & Simulated Systems**

[![Live Demo](https://img.shields.io/badge/Demo-Suspended-8b949e?style=for-the-badge&logo=render&logoColor=white)](https://genesis-chbz.onrender.com/)
[![C++](https://img.shields.io/badge/C%2B%2B17-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)](#)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](#)
[![WebSockets](https://img.shields.io/badge/Live_Telemetry-WebSockets-010101?style=for-the-badge&logo=socket.io&logoColor=white)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#)

<br/>

*Real-time NeuroEvolution (NEAT) · Native C++ Topologies · Asynchronous Physics Streaming*

---

</div>

> [!NOTE]
> The live demo is currently suspended. Render's free tier provides 720 instance hours per month, and that allowance has been used up, so the service stays offline until it resets.

> **Proprietary Engine Notice:**  
> This repository serves strictly as a public architectural showcase. To protect the intellectual property and prevent automated LLM replication, explicit C++ source code, internal WebSocket serialization schemas, and structural build files have been abstracted. **The actual engine source code is private.** When the [Live Demo](https://genesis-chbz.onrender.com/) is online, you can watch the neural networks evolve in real-time.

---

## The Concept: Evolving, Not Programming

GENESIS is a high-performance artificial intelligence sandbox engineered entirely from scratch. Instead of programming algorithmic logic to navigate a 2D physics track, GENESIS forces vehicles to **evolve** a brain.

The simulation lifecycle runs continuously:
1. **Simulation:** A population of autonomous vehicles navigates a track. Each vehicle uses raw ray-casting sensors to "see" the distance to solid walls.
2. **Evaluation:** A dynamic neural network processes this sensory array into raw steering and acceleration telemetry. Vehicles are scored solely on forward distance traveled before collision.
3. **Evolution:** The bespoke NEAT (NeuroEvolution of Augmenting Topologies) engine culls the weak, selecting the elite performers to mutate. The engine dynamically grows new hidden neurons, wires new synapses, and perturbs weights to forge the next generation.

Over time, you can watch the raw neural topologies organically grow in complexity as the population learns to master the environment.

---

## Architectural Breakdown

To achieve real-time topological mutation and 60 FPS physics streaming in the browser, the architecture relies on strict boundaries between computation, orchestration, and rendering. 

### 1. The Evolutionary Core (C++17)
The mathematical heart of GENESIS is a highly optimized, zero-dependency implementation of the NEAT algorithm written in modern C++.
* **Dynamic Topologies:** Instead of relying on static matrix multiplication like standard deep learning, this engine handles complex, non-linear, and recurrent graph structures.
* **Innovation Tracking:** The engine strictly tracks historical genomic mutations across the population to perform structural speciation and crossover without topology collisions.
* **Pre-allocated Math:** Feed-forward activations avoid standard dynamic memory allocation in the hot-path, heavily utilizing pointer arithmetic and contiguous memory for blistering fast generation cycles.

### 2. The Telemetry Bridge (Python 3.11 / FastAPI)
Python sits strictly in the middle, handling asynchronous orchestration without blocking the evolutionary math.
* **Interop Boundary:** We cross the C++/Python boundary using `pybind11`, directly passing genomic state out of the native engine.
* **Asynchronous Streaming:** FastAPI acts as a high-throughput multiplexer. The 2D physics simulation loop runs continuously, buffering positional vectors and network topologies, and blasting them to the client via a persistent WebSocket connection.

### 3. The Visualization Dashboard (Vanilla HTML/JS)
The frontend is built with zero heavy frameworks, relying entirely on highly optimized HTML5 Canvas rendering.
* **Live Topology Rendering:** As the C++ engine mutates the networks, the frontend dynamically draws the expanding brains using live Bezier curves.
* **Real-time Engine Controls:** The UI maintains a bi-directional pipe to throttle the background C++ engine loop, allowing you to slow down the generation rate to watch individual vehicles learn, or uncap it to speed-run evolution.

---

## The `.nue` Engine Format

Because neural topologies are dynamically generated, GENESIS utilizes a proprietary binary serialization format. 

**Binary Serialization (`.nue` files):** 
The system supports hot-swapping brains. Users can serialize the current champion's topology into a highly compressed, encrypted `.nue` (Neural Evolution Encrypted) binary file, and inject it back into the engine later to resume evolution.

> **Example File Included:** This repository includes a sample `.nue` file. Once the [Live Demo](https://genesis-chbz.onrender.com/) is back online, you can download this file directly from this repo and upload it using the "Load Genome" button to watch a pre-trained brain navigate the track instantly.

---

## Internal System Lifecycle

*(Note: The following represents the internal deployment pipeline used to serve the private backend)*

1. **Compilation Phase:** The CMake toolchain aggressively optimizes the `genesis_engine` C++ source into a native compiled Python extension.
2. **Server Initialization:** Uvicorn spins up the async event loop, binding the WebSocket endpoints and loading the initial C++ population state into memory.
3. **Continuous Streaming:** The simulation loops infinitely, calculating physics, evaluating fitness, and streaming telemetry back to any connected browser clients.

---

## License

This architectural showcase and its associated `.nue` sample files are provided under the MIT License. *(Note: The core C++ engine itself remains proprietary).*

Copyright (c) 2026 Anshuman

<div align="center">

*Engine and Architecture designed by [Anshuman](https://github.com/AnshumanJ28)*

</div>
