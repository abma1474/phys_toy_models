# phys_toy_models

A collection of computational toy physics models.
---

## 📋 Included Notebooks

### 1. `pisr_heat_diffusion.ipynb` — Physics-Informed Symbolic Regression (PISR)
* **Overview:** Demonstrates extracting analytical equations from noisy observational data while enforcing known physical laws.
* **Physics Domain:** 1D Heat Diffusion Equation ($\frac{\partial u}{\partial t} = \alpha \frac{\partial^2 u}{\partial x^2}$).
* **Key Libraries:** `PySR`, `SymPy`, `NumPy`.
* **Methodology:**
  1. Generates synthetic spacetime grid data $u(x,t) = e^{-\alpha t} \sin(x)$ with injected Gaussian noise.
  2. Runs symbolic regression using PySR to generate candidate expressions.
  3. Evaluates candidate expressions against a custom physics-informed loss function:
     $$\text{Total Loss} = \text{Data Loss} + \lambda \times \text{Physics Residual Loss}$$
  4. Ranks candidate equations to recover the underlying heat diffusion model.

---

### 2. `leapfrog_nbody_simulation.ipynb` — N-Body Orbital Mechanics (Leapfrog Integrator)
* **Overview:** Implements a second-order Leapfrog integration scheme to simulate gravitational trajectories in N-body dynamical systems.
* **Physics Domain:** Gravitational N-Body Dynamics (Sun-Earth System).
* **Key Libraries:** `NumPy`, `Matplotlib`, `Pandas`, `forces` (custom module).
* **Methodology:**
  1. Implements `leapfrogStep()` to update positions, accelerations, and velocities over a single time step.
  2. Runs multi-step numerical integration via `calculateTrajectories()`.
  3. Models a 1000-day Sun-Earth orbital trajectory and plots spatial coordinates over time.

---

## 🛠️ Requirements & Installation

Install the required Python packages before running the notebooks:

```bash
pip install numpy pandas matplotlib sympy pysr
