# Problem 2
#  Task 1: Governing Equation and Small-Angle Approximation

###  Objective:
To derive the approximate solutions of the **forced damped pendulum** under the small-angle approximation and explore the **resonance conditions** and their implications on the system’s energy.

---

##  Governing Differential Equation

The motion of a **forced damped pendulum** is described by the following second-order nonlinear differential equation:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \sin(\theta) = A \cos(\omega t)
$$

Where:

- $\theta(t)$: angular displacement (in radians)
- $b$: damping coefficient (viscous damping)
- $g$: acceleration due to gravity
- $L$: length of the pendulum
- $A$: amplitude of external driving force
- $\omega$: angular frequency of external driving force

---

##  Small-Angle Approximation

For **small angles** ($|\theta| \ll 1$), we can linearize the equation using:

$$
\sin(\theta) \approx \theta
$$

This transforms the original nonlinear equation into a **linear second-order nonhomogeneous ODE**:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \theta = A \cos(\omega t)
$$

Let:
- $\omega_0^2 = \frac{g}{L}$ be the **natural angular frequency** of the pendulum.

Then the equation becomes:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \omega_0^2 \theta = A \cos(\omega t)
$$

---

##  General Solution Structure

This equation has a solution of the form:

$$
\theta(t) = \theta_{\text{hom}}(t) + \theta_{\text{part}}(t)
$$

###  Homogeneous Solution (Transient):

Solution to the undriven, damped system:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \omega_0^2 \theta = 0
$$

This has solutions depending on the damping regime:
- Underdamped ($b^2 < 4\omega_0^2$): Oscillatory decay
- Critically damped ($b^2 = 4\omega_0^2$): Fastest return without oscillation
- Overdamped ($b^2 > 4\omega_0^2$): Slow return to equilibrium

### Particular Solution (Steady-State):

We assume a particular solution of the form:

$$
\theta_{\text{part}}(t) = C \cos(\omega t - \delta)
$$

Where:
- $C$: amplitude of the steady-state oscillation
- $\delta$: phase lag

Substituting into the differential equation, we find:

$$
C = \frac{A}{\sqrt{(\omega_0^2 - \omega^2)^2 + b^2 \omega^2}}
$$

$$
\tan(\delta) = \frac{b \omega}{\omega_0^2 - \omega^2}
$$

---

##  Resonance and Energy Implications

###  Resonance Condition:

Resonance occurs when the **denominator of $C$ is minimized**, i.e., when:

$$
\omega \approx \omega_{\text{res}} = \sqrt{\omega_0^2 - \frac{b^2}{2}}
$$

This is the **resonant frequency** of the forced damped oscillator — slightly lower than the natural frequency due to damping.

###  Amplitude at Resonance:

At resonance, amplitude is maximized:

$$
C_{\text{max}} = \frac{A}{b \omega_{\text{res}}}
$$

Small damping $b$ leads to very **large amplitudes** — a hallmark of resonance.

###  Energy Considerations:

The total energy of the pendulum is the sum of kinetic and potential energies. In the presence of damping and driving force:
- The **external force pumps energy into the system**.
- **Damping dissipates energy** as heat.
- At steady state, the energy **input from the driver balances dissipation**, leading to a sustained oscillation.

Resonance implies **maximum energy transfer** from the driver to the pendulum.

---

##  Summary

- The forced damped pendulum becomes a **linear ODE** under small-angle approximation.
- The system exhibits **resonance** at a specific driving frequency.
- The amplitude and phase of oscillation depend on the balance between **restoring**, **damping**, and **driving** forces.
- Resonance leads to **large amplitudes and high energy**, which must be managed in engineering systems.

In Task 2, we will simulate the system numerically using Python and visualize how amplitude varies with driving frequency — including resonance and damping effects.
