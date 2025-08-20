# Ideal model

This repository demonstrates a **simple 1D vertical control model** for a rotorcraft (quadcopter) assuming:

- No roll/pitch/yaw dynamics.
- Only vertical (axial) motion.
- Known trajectory `h(t)` with desired velocity and acceleration.

## Controller
The model assumes perfect dynamics:  

$$m \ddot h = T - mg$$

We use a **feedforward + feedback** design:

- **Feedforward** thrust:  
  $$T_{ff}(t) = m \cdot (g + a_d(t))$$

  where $a_d(t)$ is the desired vertical acceleration.

- **Feedback** (PID on height and velocity):  
  $$a_{fb} = K_p (h_d - h) + K_d (v_d - v) + K_i \int (h_d - h)\, dt$$

- **Total thrust:**  
  $T^\*(t) = m \cdot \big(g + a_d(t) + a_{fb}\big)$

## Files

- `controller.py` : Python simulation of the system, logs trajectories, and plots results.
- `README.md` : This file.

## Usage

```bash
python controller.py
