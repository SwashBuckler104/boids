# Boids — Swarm Intelligence Simulation
### Module 7 · Drone Swarm Lecture

A [Craig Reynolds](https://www.red3d.com/cwr/boids/) boids simulation originally written in **Processing**, 
paired with an HTML lecture presentation demonstrating the three fundamental flocking rules.

---

## Repository Contents

| File | Description |
|---|---|
| `boids.pde` | Main Processing sketch — setup, draw loop, keyboard controls |
| `Boid.pde` | Boid class — separation, alignment, cohesion, neighbour finding |
| `Avoid.pde` | Static obstacle class |
| `boids.html` | Self-contained HTML/JS lecture presentation with live demos |
| `requirements.md` | Conceptual prerequisites and environment requirements |
| `requirements.txt` | Python dependencies (for any Python tooling) |

---

## Quick Start

### Option A — HTML Presentation (no install required)

Open `boids.html` directly in any modern browser:

```bash
# From the repo root
open boids.html          # macOS
open boids.html      # Linux
start boids.html         # Windows
```

The presentation is fully self-contained. An internet connection is needed only for KaTeX (math rendering); the simulations run locally in JavaScript.

---

### Option B — Processing Sketch (interactive simulation)

**Install Processing 4:**  
Download from [processing.org](https://processing.org/download)

**Run the sketch:**

1. Open Processing IDE
2. `File → Open` → navigate to this folder → select `boids.pde`
3. Click the **Play** button (▶)

**In-sketch keyboard controls:**

| Key | Action |
|---|---|
| `q` | Tool: add boids (click canvas) |
| `w` | Tool: place obstacles (click canvas) |
| `e` | Tool: eraser |
| `1` | Toggle **alignment** on/off |
| `2` | Toggle **separation** on/off |
| `3` | Toggle **obstacle avoidance** on/off |
| `4` | Toggle **cohesion** on/off |
| `5` | Toggle **noise** on/off |
| `-` / `=` | Decrease / increase global scale |
| `,` | Reset obstacles to walls |
| `.` | Reset obstacles to circle |

---

## The Three Flocking Rules

Each boid applies three local steering forces every frame:

### 1. Separation
Steer away from neighbours closer than `crowdRadius` (≈ 46 units).  
Prevents collisions and pile-ups.

### 2. Alignment
Steer toward the distance-weighted average heading of neighbours within `friendRadius` (60 units).  
Produces coordinated direction of travel.

### 3. Cohesion
Steer toward the centre of mass of nearby neighbours.  
Keeps the flock together as a loose whole.

See `boids.html` for the full mathematical formulas and live visual demos.

---

## Drone Swarm Connection

| Boid Rule | Drone Swarm Equivalent |
|---|---|
| Separation | Collision avoidance envelope (ADS-B / UWB ranging) |
| Alignment | Formation holding via MAVLink heading sharing |
| Cohesion | Flock integrity / comms-range management |
| Obstacle avoidance | Geofence / LiDAR-based terrain following |
| Noise term | Robustness against degenerate configurations |

---

## Source

Original repository: <https://github.com/jackaperkins/boids>  
Algorithm: Reynolds, C. W. (1987). *Flocks, Herds, and Schools: A Distributed Behavioral Model.* SIGGRAPH '87.
