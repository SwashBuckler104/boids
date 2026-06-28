# Requirements — Boids Simulation & Presentation
### Module 7 · Drone Swarm Lecture

---

## 1. Conceptual Prerequisites

Students should be familiar with:

- **2D vectors** — position, velocity, addition, normalisation
- **Euclidean distance** — used to define neighbourhood radius
- **Weighted averaging** — inverse-distance weighting in alignment
- **Basic kinematics** — how a velocity vector moves a position each frame
- Basic understanding of **autonomous systems / UAVs** (Module 1–6 content)

---

## 2. HTML Presentation (`presentation.html`)

### Minimum Requirements

| Requirement | Detail |
|---|---|
| Web browser | Chrome 90+, Firefox 88+, Safari 14+, or Edge 90+ |
| JavaScript | Must be enabled |
| Screen resolution | 1024 × 768 minimum; 1280 × 800 recommended |

### Optional (for math rendering)
- Internet connection for **KaTeX** CDN (`cdn.jsdelivr.net`)
- Without it the formulas fall back to raw LaTeX source — all simulations still run

### No installation needed. Open `presentation.html` directly.

---

## 3. Processing Sketch (`boids.pde`)

### Requirements

| Requirement | Version | Notes |
|---|---|---|
| [Processing](https://processing.org/download) | 4.x (recommended) or 3.x | Free, cross-platform |
| Java | Bundled with Processing | No separate install needed |
| RAM | 512 MB minimum | 1 GB recommended for >200 boids |
| Display | 1024 × 576 minimum | Sketch window is fixed at this size |

### Installation Steps

1. Download and install Processing from [processing.org](https://processing.org/download)
2. Clone or download this repository
3. Open `boids.pde` in the Processing IDE  
   *(Processing automatically finds `Boid.pde` and `Avoid.pde` in the same folder)*
4. Press **▶ Run**

---

## 4. Python Tooling (optional)

If you wish to run any analysis scripts or serve the HTML locally:

```bash
pip install -r requirements.txt
```

Then serve locally:

```bash
python -m http.server 8080
# Open http://localhost:8080/presentation.html
```

---

## 5. Recommended Lecture Setup

| Item | Recommendation |
|---|---|
| Display | Projector or display at ≥ 1280 × 800 |
| Browser tab | Open `presentation.html` in full-screen (F11) |
| Processing | Running in a second monitor or alt-tab for live demo |
| Network | Optional — only needed for KaTeX math rendering |

---

## 6. Known Limitations

- **Processing sketch** — no built-in export; screen-record for video
- **HTML simulation** — performance degrades past ~300 boids on older hardware
- **KaTeX fallback** — offline use shows raw `$$...$$` notation instead of rendered math
