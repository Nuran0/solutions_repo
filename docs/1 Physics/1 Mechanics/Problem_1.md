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

In the next task, we will simulate these trajectories using Python to visualize how the range changes with angle $\theta$.

