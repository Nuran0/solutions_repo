# Problem 1
#  Investigating the Range as a Function of the Angle of Projection  
##  Task 1: Theoretical Foundation

###  Objective:
To derive the governing equations of projectile motion from first principles and understand how variations in initial conditions lead to a family of solutions.

---

###  Fundamental Principles

We begin with **Newton’s Second Law of Motion** applied to two-dimensional projectile motion under gravity:

- The only force acting on the object (ignoring air resistance) is gravity.
- Acceleration due to gravity is constant and acts downward with magnitude $g$.

Let the object be projected with an initial velocity $v_0$ at an angle $\theta$ to the horizontal.

---

###  Equations of Motion

We split the motion into **horizontal (x)** and **vertical (y)** components.

- Horizontal acceleration: $a_x = 0$
- Vertical acceleration: $a_y = -g$

Initial velocity components:
- $v_{0x} = v_0 \cos(\theta)$
- $v_{0y} = v_0 \sin(\theta)$

Using basic kinematic equations:

#### Horizontal Motion:
$$
x(t) = v_0 \cos(\theta) \cdot t
$$

#### Vertical Motion:
$$
y(t) = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
$$

---

###  Time of Flight

The projectile returns to the same vertical level when $y(t) = 0$ (assuming it lands at the same height it was launched):

$$
0 = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2
$$

Factor out $t$:
$$
t \left( v_0 \sin(\theta) - \frac{1}{2} g t \right) = 0
$$

Ignoring the trivial solution $t = 0$, we get:
$$
t = \frac{2 v_0 \sin(\theta)}{g}
$$

---

### Range of the Projectile

To find the horizontal **range $R$**, substitute the total time of flight into $x(t)$:

$$
R = v_0 \cos(\theta) \cdot \frac{2 v_0 \sin(\theta)}{g}
$$

Using the identity $\sin(2\theta) = 2 \sin(\theta) \cos(\theta)$:

$$
R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}
$$

---

### Family of Solutions

The above equation defines a **family of parabolic trajectories**, each determined by a specific launch angle $\theta$ and initial velocity $v_0$. For a fixed $v_0$:

- As $\theta$ varies, so does the range $R(\theta)$.
- Maximum range occurs at $\theta = 45^\circ$, where $\sin(2\theta) = 1$.
- Pairs of angles $(\theta, 90^\circ - \theta)$ give the same range due to the symmetry of the sine function.

---

###  Summary of Governing Equations:

- **Horizontal motion**: $x(t) = v_0 \cos(\theta) \cdot t$
- **Vertical motion**: $y(t) = v_0 \sin(\theta) \cdot t - \frac{1}{2} g t^2$
- **Time of flight**: $T = \frac{2 v_0 \sin(\theta)}{g}$
- **Range**: $R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}$

---

#  Task 2: Analysis of the Range

###  Objective:
To investigate how the **horizontal range** of a projectile depends on the **angle of projection** and how variations in **initial velocity** ($v_0$) and **gravitational acceleration** ($g$) influence this relationship.

---

###  Recap: Range Equation

From Task 1, we derived the horizontal range of a projectile as:

$$
R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}
$$

This formula clearly shows that the range:
- Depends on $\sin(2\theta)$, which peaks at $2\theta = 90^\circ$ → $\theta = 45^\circ$.
- Is directly proportional to the square of the initial velocity $v_0$.
- Is inversely proportional to gravitational acceleration $g$.

---

###  Python Simulation

Below is a Python script to visualize how the range varies with projection angle for different values of $v_0$ and $g$.

```python
import numpy as np
import matplotlib.pyplot as plt

def compute_range(theta_deg, v0, g):
    theta_rad = np.radians(theta_deg)
    return (v0 ** 2) * np.sin(2 * theta_rad) / g

angles = np.linspace(0, 90, 500)

# Parameters for comparison
v0_values = [10, 20, 30]
g_values = [9.8, 1.6, 24.8]  # Earth, Moon, Jupiter

plt.figure(figsize=(10, 6))

# Plot for different initial velocities on Earth
for v0 in v0_values:
    ranges = compute_range(angles, v0, 9.8)
    plt.plot(angles, ranges, label=f'v₀ = {v0} m/s (g = 9.8 m/s²)')

plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Range (meters)')
plt.title('Range vs Angle for Different Initial Velocities (g = 9.8)')
plt.legend()
plt.grid(True)
plt.show()

# Plot for different gravity environments (fixed v0)
plt.figure(figsize=(10, 6))
v0_fixed = 20
for g in g_values:
    ranges = compute_range(angles, v0_fixed, g)
    plt.plot(angles, ranges, label=f'g = {g} m/s²')

plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Range (meters)')
plt.title(f'Range vs Angle for Different Gravity (v₀ = {v0_fixed} m/s)')
plt.legend()
plt.grid(True)
plt.show()


