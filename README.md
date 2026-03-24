# 6CCM359A — Numerical and Computational Methods with Python

> **Mock Class Test — Model Solutions**  
> BSc and MSci Examination | King's College London | December 2023  
> Time allowed: 2 hours + 20 minutes submission time

---

## Overview

This repository contains the model solutions (`mocktest_sol.ipynb`) for the mock class test of **6CCM359A Numerical and Computational Methods with Python**. The notebook covers seven questions spanning core Python and numerical computing skills, implemented using `numpy` and `matplotlib`.

---

## Requirements
```bash
pip install numpy matplotlib
```

No additional packages are required beyond the standard scientific Python stack.

---

## Question Summary

| # | Topic | Points | Key Concepts |
|---|-------|--------|--------------|
| Q1 | Arithmetic | 15 | `np.exp`, `np.log`, `np.cos`; list comprehensions for series sums |
| Q2 | Lists | 20 | List construction with conditionals, slicing, stride indexing |
| Q3 | Vectors and matrices | 20 | `np.array`, outer product, identity matrix, `np.linalg.inv` |
| Q4 | Functions and plots | 15 | Lambda-style function definitions, `np.linspace`, `plt.plot` |
| Q5 | Sequences | 20 | Logistic map iteration, index search over difference sequences |
| Q6 | Lagrange interpolation | 20 | Basis polynomial construction, polynomial interpolation |
| Q7 | ODE — Verlet scheme | 20 | Second-order ODE, Verlet time-stepping, error vs analytical solution |

**Total: 110 points**

---

## Question Details

### Q1 — Arithmetic
Evaluates $a = e^{\ln(\pi)\cos(5)+3}$ and constructs the series
$f(x) = \sum_{j=3}^{200} \frac{1}{1+xj^2}$
using a list comprehension passed to `sum()`.

### Q2 — Lists
Constructs a 67-element piecewise list `v1`, extracts a contiguous slice `v2` (indices 24–43), and builds a reverse stride slice `v3` of even-indexed elements from the end.

### Q3 — Vectors and Matrices
Converts `v1` to a numpy array `w`, builds the rank-1 update matrix $A = I + ww^T$ via a double loop, then solves $Az = w$ using `np.linalg.inv`.

### Q4 — Functions and Plots
Defines $g(x) = \cos(\pi e^x)$ and $h(x) = \sin(\pi e^x)$, then plots both $g(x)$ and $g(x) + h(x)$ over $x \in [-5, 2]$ using at least 200 grid points.

### Q5 — Sequences
Implements the logistic map $r(x) = 4x(1-x)$, generates the orbit $(x_0, \ldots, x_{34})$ starting from $x_0 = 0.3$, and writes `ma(n)` to find the index of the maximum difference $x_m - x_{m+1}$ over $m \in \{0,\ldots,n\}$.

### Q6 — Lagrange Interpolation
Implements the Lagrange basis polynomial `pp(i, x, xs)`, sets up the four data points $(0.1, 10),\ (0.2, 5),\ (0.3, -3),\ (0.4, -8)$, and builds the interpolant `inter(x)` as a weighted sum of basis polynomials.

### Q7 — Verlet Scheme
Implements the Verlet integrator for $y'' = F(y)$:
$$y_{n+1} = 2y_n - y_{n-1} + h^2 F(y_n)$$
Solves for $F(y) = -y$ with $y_0 = 0$, $y_1 = h = 0.1$ over 100 steps, and compares the numerical result at $x = 4.8$ against the analytical solution $y(x) = \sin(x)$.

---

## Usage
```bash
jupyter notebook mocktest_sol.ipynb
```

Run all cells in order. Each solution block is delimited by `### BEGIN SOLUTION` and `### END SOLUTION` markers, followed by assertion-based tests that print partial credit messages on success.

---

## Notes

- No calculators were permitted during the original exam.
- The `mathsolution` module imported at the top is used internally for reference checks and does not need to be installed separately in a personal environment — replace with `math` if running outside the exam system.
- All floating-point assertions use `abs_tol=1e-12` unless otherwise stated.
