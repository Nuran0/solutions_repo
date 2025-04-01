# Problem 3

## Analysis of Possible Trajectories for a Payload Released Near Earth

When a payload is released near Earth, its trajectory depends on several factors, including its initial velocity, the angle of release, and the gravitational influence of Earth. The most common types of trajectories for objects near Earth are **parabolic**, **hyperbolic**, and **elliptical**. These trajectories are determined by the object's velocity relative to Earth and the gravitational force exerted by Earth.

### 1. **Gravitational Force and Energy Considerations**

The gravitational force $F$ acting on an object near Earth is given by Newton’s law of gravitation:

$$
F = \frac{G M m}{r^2}
$$

Where:
- $G$ is the gravitational constant ($6.67430 \times 10^{-11} \, \text{m}^3 \, \text{kg}^{-1} \, \text{s}^{-2}$),
- $M$ is the mass of Earth ($5.972 \times 10^{24} \, \text{kg}$),
- $m$ is the mass of the object,
- $r$ is the distance between the object and the center of Earth.

To describe the trajectory, we need to consider the specific mechanical energy $\epsilon$ of the object, which is the sum of its kinetic energy and potential energy:

$$
\epsilon = \frac{v^2}{2} - \frac{GM}{r}
$$

Where:
- $v$ is the velocity of the object at a given point,
- $r$ is the distance from the center of Earth.

Based on the specific mechanical energy, the trajectory type can be classified into three categories:

### 2. **Elliptical Trajectory**

An elliptical trajectory occurs when the object’s velocity is lower than the escape velocity, but it is still sufficient to form an elliptical orbit around Earth. The object's total energy $\epsilon$ is negative in this case.

#### Condition for Elliptical Trajectory:
For an elliptical orbit, the total energy of the object must be negative:

$$
\epsilon < 0
$$

This means the object is in a bound orbit around Earth. The object will travel in an ellipse, coming closest to Earth at the periapsis (the point of closest approach) and farthest from Earth at the apoapsis.

The orbital parameters of an elliptical orbit are determined by:
- **Semi-major axis** $a$,
- **Eccentricity** $e$.

The relationship between the semi-major axis and the specific orbital energy is given by:

$$
\epsilon = -\frac{GM}{2a}
$$

Where:
- $a$ is the semi-major axis of the ellipse,
- $e$ is the orbital eccentricity, which measures the deviation from a perfect circle.

### 3. **Parabolic Trajectory**

A parabolic trajectory is the special case of an elliptical orbit where the object’s velocity is exactly equal to the escape velocity at a given distance. In this case, the total mechanical energy $\epsilon$ is zero:

$$
\epsilon = 0
$$

#### Condition for Parabolic Trajectory:
For an object to follow a parabolic trajectory, its velocity must be equal to the escape velocity at the point of release:

$$
v = \sqrt{\frac{2GM}{r}}
$$

This velocity is the minimum speed required to escape Earth’s gravitational influence without ever returning, but in a manner that the object’s trajectory forms a parabola. A parabolic trajectory does not form a closed orbit; it is an open curve.

### 4. **Hyperbolic Trajectory**

A hyperbolic trajectory occurs when the object's velocity exceeds the escape velocity at a given distance from Earth. In this case, the total mechanical energy $\epsilon$ is positive:

$$
\epsilon > 0
$$

#### Condition for Hyperbolic Trajectory:
For an object to follow a hyperbolic trajectory, its velocity must be greater than the escape velocity at the point of release:

$$
v > \sqrt{\frac{2GM}{r}}
$$

This means the object has more than enough energy to escape Earth’s gravitational pull and will follow a hyperbolic path. Hyperbolic trajectories are unbound, meaning the object will not return to Earth, and will continue traveling through space.

### 5. **Graphical Representation of Trajectories**

To better visualize the differences in these trajectories, we can plot the paths of the object depending on its initial velocity. Let's simulate and plot these trajectories for a payload released near Earth.

#### Python Code for Trajectory Simulation:

![alt text](image-2.png)
