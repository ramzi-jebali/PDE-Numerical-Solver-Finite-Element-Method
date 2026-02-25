# Finite Element Method (FEM) Solver for PDEs

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Scipy](https://img.shields.io/badge/Library-SciPy_Sparse-green.svg)](https://scipy.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📌 Project Overview
This repository contains a complete numerical pipeline for solving Partial Differential Equations (PDEs) using the **Finite Element Method (FEM)**. Developed during the ANN201/ANN1 course at **ENSTA Paris**, the project focuses on the implementation of a solver for the **Helmholtz equation** and Poisson problems on complex meshes.

The project demonstrates the transition from continuous mathematical models to discrete numerical implementations, emphasizing computational efficiency through sparse matrix algebra.

## 🧮 Mathematical Framework
We solve the Helmholtz equation with various boundary conditions (Dirichlet, Neumann, Fourier):

$$- \Delta u + k^2 u = f \quad \text{in } \Omega$$

### Variational Formulation
The problem is transformed into its weak form. Find $u \in H^1(\Omega)$ such that:
$$\int_{\Omega} \nabla u \cdot \nabla \bar{v} \, d\Omega + k^2 \int_{\Omega} u \bar{v} \, d\Omega = \int_{\Omega} f \bar{v} \, d\Omega + \int_{\Gamma_N} g_N \bar{v} \, d\gamma$$
where $v$ is a test function in the appropriate Sobolev space.

## 🚀 Technical Implementation
* **Triangular Meshing:** Integration of mesh data (nodes, elements) for complex 2D domains.
* **Matrix Assembly:** Implementation of local-to-global assembly for Stiffness ($P_1$ Lagrange elements) and Mass matrices.
* **Boundary Conditions:** Specialized treatment for:
    * **Dirichlet:** Implementation via pseudo-elimination.
    * **Neumann & Fourier:** Surface integrals integration in the second member.
* **Optimization:** Use of `scipy.sparse` for efficient storage and resolution of large-scale linear systems.

## 📊 Key Results
* **Convergence Analysis:** Validation of the solver by comparing numerical solutions ($u_h$) with analytical solutions across different mesh sizes.
* **Error Estimation:** Computation of $L^2$ and $H^1$ error norms to verify the theoretical convergence rates.

## 📂 Repository Structure
* `ramzi_jebali.ipynb`: Fundamental implementation of $P_1$ finite elements and basic PDE solving.
* `TP2-helmholtz.ipynb`: Advanced application to the Helmholtz equation with non-homogeneous boundary conditions.
* `src/`: Utility scripts for mesh handling and visualization.

## 💻 Tech Stack
* **Language:** Python
* **Scientific Computing:** NumPy, SciPy (Sparse solvers)
* **Visualization:** Matplotlib
