# Programming-Assignment-Module-2-
To model the single-stranded RNA structure of SARS-CoV-2 (Covid-19) using parametric mathematical equations and visualize it using Python. The model should also estimate the length of the RNA curve over the interval  0 &lt; 𝑡 &lt; 3 0&lt;t&lt;3.

Here is the **complete assignment solution** for the SARS-CoV-2 RNA mathematical modeling and visualization task, including well-documented Python code and explanation. A README content is also included for submission.

---

### ✅ **Assignment: SARS-CoV-2 RNA Mathematical Modeling and 3D Visualization**

#### 🔬 **Objective:**

To model the **single-stranded RNA structure** of SARS-CoV-2 (Covid-19) using parametric mathematical equations and visualize it using Python. The model should also estimate the length of the RNA curve over the interval $0 < t < 3$.

---

### 📌 **Mathematical Model**

Given parametric equations for RNA:

* $x(t) = \sqrt{8} \cdot \sqrt{\frac{1 - \cos(2t)}{\sqrt{2}}}$
* $y(t) = \sqrt{8} \cdot \sin(t + 90^\circ)$
* $z(t) = t$

Note:

* Convert 90° to radians: $90^\circ = \frac{\pi}{2}$

---

### 🧠 **Python Implementation**

```python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from scipy.integrate import simps

# Define time interval
t = np.linspace(0, 3, 1000)

# Parametric equations
x = np.sqrt(8) * np.sqrt((1 - np.cos(2 * t)) / np.sqrt(2))
y = np.sqrt(8) * np.sin(t + np.pi/2)  # 90 degrees = pi/2 radians
z = t

# Calculate curve length using arc length formula
dx = np.gradient(x, t)
dy = np.gradient(y, t)
dz = np.gradient(z, t)
curve_length = simps(np.sqrt(dx**2 + dy**2 + dz**2), t)

print(f"Estimated RNA structure length from t=0 to t=3: {curve_length:.4f} units")

# 3D Line Plot
fig = plt.figure(figsize=(10, 7))
ax = fig.add_subplot(111, projection='3d')
ax.plot(x, y, z, color='red', linewidth=2)

# Labels and View
ax.set_title("3D Structure of SARS-CoV-2 RNA", fontsize=14)
ax.set_xlabel("x(t)")
ax.set_ylabel("y(t)")
ax.set_zlabel("z(t)")
ax.grid(True)

plt.tight_layout()
plt.show()
```

---

### 📊 **Output**

* **3D continuous line plot** showing RNA path.
* **Estimated RNA structure length** from $t=0$ to $t=3$ units is displayed in console.

---

### 📄 **README Content (For Report Submission)**

```markdown
# SARS-CoV-2 RNA Mathematical Modeling & 3D Visualization

## Objective
This assignment aims to mathematically model the single-stranded RNA structure of the SARS-CoV-2 (Covid-19) virus and visualize it using a 3D plot. The visualization is based on a set of given parametric equations.

## Description
- Images obtained from Thermo Fisher Scientific™ TEM and RNA schematics were used to understand the virus structure.
- The RNA trajectory is modeled using the following parametric equations:

```

x(t) = √8 \* sqrt((1 - cos(2t)) / √2)
y(t) = √8 \* sin(t + 90°)
z(t) = t

````

- The Python script:
- Calculates the coordinates for the RNA model.
- Uses numerical integration (Simpson's rule) to estimate the curve length from t = 0 to t = 3.
- Plots a smooth 3D visualization using `matplotlib`.

## Tools Used
- Python 3
- NumPy
- Matplotlib
- SciPy

## Output
- A 3D plot of the SARS-CoV-2 RNA structure
- Estimated RNA curve length: ~`<value>` units

## How to Run
1. Install required packages:
 ```bash
 pip install numpy matplotlib scipy
````

2. Run the Python script in any IDE or notebook environment.


