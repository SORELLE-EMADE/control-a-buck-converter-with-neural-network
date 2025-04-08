# Buck Converter Simulation with Perturbation and Control

This repository contains a simulation of a **Buck Converter** under different operating conditions, implemented in Python using the Jupyter Notebook format.

The simulation explores how a DC-DC buck converter behaves under:
- Normal conditions (before any perturbation),
- During disturbance (perturbation phase),
- And under control action (feedback control applied after disturbance).

---

## Objectives

The main goals of this project are:

1. **To simulate the dynamics of a buck converter**:
   - Using differential equations and discrete time steps.
   - Observing how output voltage and inductor current evolve over time.

2. **To analyze the effect of perturbations**:
   - By introducing a disturbance (e.g., a change in load or input voltage) during the simulation.
   - Visualizing the impact on system stability.

3. **To implement and test a control strategy**:
   - Applying a **duty cycle correction** to recover nominal operation.
   - Observing the controlled response and performance of the converter.

---

##  Simulation Phases

The notebook provides plots and visualizations for each of the following phases:

### Before Perturbation
*Insert here a figure showing the voltage and current evolution under normal conditions.*

> _Example placeholder:_
> ![Before Perturbation](figures/before_perturbation.png)

---

### ⚠ After Perturbation
*Insert here a figure showing the disturbance effect (e.g., sudden drop in input voltage or load variation).*

> _Example placeholder:_
> ![After Perturbation](figures/after_perturbation.png)

---

### 🎯 Control Phase
*Insert here a figure showing how the system recovers after the control is applied.*

> _Example placeholder:_
> ![Control](figures/control_response.png)

---

##  Duty Cycle and Control Logic

- The duty cycle (`D`) is a key parameter used to regulate the output voltage.
- In the simulation:
  - The initial `D` is set to regulate a nominal output.
  - When the perturbation occurs, `D` is recalculated or adjusted using a simple control rule.
  - The goal is to maintain the output voltage around a desired reference value.

---

##  How to Run the Simulation

### Prerequisites
Make sure you have the following installed:

- Python 3.x
- Jupyter Notebook
- NumPy
- Matplotlib


