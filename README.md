#  Buck Converter Simulation — Perturbation Analysis & Control Strategy

This repository provides a **complete simulation of a Buck (step-down) converter**, modeled using Python in a Jupyter Notebook environment. The converter is subjected to **external perturbations**, and a simple **feedback control mechanism** is implemented to stabilize the output.

The simulation is structured in three distinct phases:

1. **Before Perturbation** — the system operates under normal steady-state conditions.
2. **After Perturbation** — a disturbance is introduced (such as load variation or input voltage drop).
3. **Control Phase** — a feedback mechanism adjusts the duty cycle to restore the output voltage.

---

## Theoretical Background

A **buck converter** is a DC-DC power converter that steps down voltage from its input to output. It is widely used in power electronics and embedded systems.

###  Key Equations

The operation of a buck converter can be modeled using the following differential equations:

- When the switch is **ON**:

\[
\frac{di_L(t)}{dt} = \frac{V_{in} - V_{out}(t)}{L}, \quad \frac{dV_{out}(t)}{dt} = \frac{i_L(t) - \frac{V_{out}(t)}{R}}{C}
\]

- When the switch is **OFF**:

\[
\frac{di_L(t)}{dt} = \frac{-V_{out}(t)}{L}, \quad \frac{dV_{out}(t)}{dt} = \frac{i_L(t) - \frac{V_{out}(t)}{R}}{C}
\]

Where:
- \( L \): Inductance
- \( C \): Capacitance
- \( R \): Load resistance
- \( i_L(t) \): Inductor current
- \( V_{out}(t) \): Output voltage
- \( V_{in} \): Input voltage

---

##  Simulation Goals

- Model the **discrete-time behavior** of the converter.
- Simulate the **evolution of the inductor current** and **output voltage** over time.
- Apply a **disturbance** to the system (such as a sudden change in input voltage).
- Implement a **simple PI-like control** on the duty cycle to maintain a constant output voltage.

---

## Simulation Phases & Plots

### 1. Before Perturbation

This phase establishes the **reference behavior** of the converter. The duty cycle is initially set based on the desired output voltage:

\[
D = \frac{V_{out}}{V_{in}}
\]

You can insert a figure like this:

> _Example Placeholder:_
> ![Before Perturbation](figures/before_perturbation.png)

---

### 2. After Perturbation

A sudden disturbance is introduced at time step \( t = t_0 \). This may represent:
- A drop in \( V_{in} \)
- A change in the load resistance \( R \)

The converter no longer maintains the reference output voltage:

\[
V_{out}(t_0^+) < V_{ref}
\]

> _Example Placeholder:_
> ![After Perturbation](figures/after_perturbation.png)

This phase highlights the converter's **vulnerability to dynamic changes**.

---

### 3. Control Phase

A **feedback mechanism** is introduced to adjust the duty cycle \( D \), aiming to bring the output voltage back to its reference value:

\[
D(t+1) = D(t) + K_p \cdot (V_{ref} - V_{out}(t))
\]

Where:
- \( K_p \): Proportional gain
- \( V_{ref} \): Desired reference voltage

This simulates a basic **proportional controller** (or P-controller).

> _Example Placeholder:_
> ![Control](figures/control_response.png)

The system is expected to **stabilize** progressively as the controller acts to compensate for the disturbance.

---

## Duty Cycle and Regulation

The **duty cycle** \( D \) is the primary control variable. It determines how much time the switch is ON during each cycle. The initial value is computed analytically:

\[
D = \frac{V_{out}}{V_{in}}
\]

But during the simulation, it evolves dynamically depending on system performance.

---

##  Example Simulation Output

You will see plots showing:
- The evolution of \( V_{out}(t) \) over time
- The inductor current \( i_L(t) \)
- The changes in duty cycle \( D(t) \)
- The moment of disturbance
- The correction applied by the controller

---

