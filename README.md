# SVM Kernel Trick: Understanding the Kernel Trick

## From Straight Lines to Complex Boundaries

A beginner-friendly machine learning tutorial demonstrating how Support Vector Machines (SVMs) use the **Kernel Trick** to classify data that cannot be separated by a straight line.

This tutorial was created as part of a postgraduate Machine Learning course assignment at the University of Hertfordshire.

---
## What This Tutorial Covers

- Why linear SVMs fail on non-linearly separable data
- How transforming data into higher dimensions solves this (with a 3D visualisation)
- What the Kernel Trick is and why it is computationally efficient
- How different kernels (Linear, Polynomial, RBF) produce different decision boundaries
- How the `gamma` parameter in the RBF kernel controls underfitting vs overfitting

---
## Repository Contents

```
├── Script.ipynb             # Main tutorial code (all plots)
├── requirements.txt         # Python dependencies
├── README.md                # This file
└── LICENSE                  # MIT Licence
```

---
## Requirements

- Python 3.8 or higher
- numpy
- matplotlib
- scikit-learn

Install all dependencies with:

```bash
pip install -r requirements.txt
```

---

## How to Run

Open `Script.ipynb` in Jupyter Notebook, JupyterLab, or VS Code with the Jupyter extension, then execute the cells in order.

Each section is clearly labelled and can be run independently.

---

## Plots Produced

Running the script generates the following plots in order:

| # | Plot | Purpose |
|---|------|---------|
| 1 | Concentric circles scatter | Shows the non-linear data that a straight line cannot separate |
| 2 | 3D kernel trick projection | Visualises how mapping x → x₁²+x₂² lifts data into 3D where it becomes separable |
| 3 | Linear SVM boundary | Demonstrates failure on non-linear data |
| 4 | Polynomial kernel boundary | Shows a curved boundary (degree=3) |
| 5 | RBF kernel boundary | Shows how RBF handles the circles cleanly |
| 6 | RBF gamma=0.1 | Smooth boundary — risk of underfitting |
| 7 | RBF gamma=1 | Balanced boundary |
| 8 | RBF gamma=10 | Tight boundary — risk of overfitting |

---

## Key Concepts

**Kernel Trick** — Instead of explicitly computing a high-dimensional transformation φ(x), the SVM computes a kernel function K(xᵢ, xⱼ) = φ(xᵢ) · φ(xⱼ) directly. This gives the same result without the computational cost of working in high dimensions.

**RBF Kernel** — K(xᵢ, xⱼ) = exp(−γ ||xᵢ − xⱼ||²). The gamma (γ) parameter controls how localised each training point's influence is on the boundary.

---

## Accessibility

- All plots use the **PiYG colourmap**, which is colourblind-friendly
- Plot titles describe what each figure shows
- All axes are labelled

---

## Licence

This project is licensed under the **MIT Licence** — see the [LICENSE](LICENSE) file for details. You are free to use, adapt, and share this code with attribution.

---

## References

- Cortes, C. & Vapnik, V. (1995). Support-vector networks. *Machine Learning*, 20(3), 273–297.
- Schölkopf, B. & Smola, A. J. (2002). *Learning with Kernels*. MIT Press.
- Scikit-learn documentation — [SVM](https://scikit-learn.org/stable/modules/svm.html)
- Cover, T. M. (1965). Geometrical and statistical properties of systems of linear inequalities. *IEEE Transactions on Electronic Computers*, EC-14(3), 326–334.