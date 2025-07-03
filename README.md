# Korea-qhack2025-QUICK

# 🧠 Korea Quantum Hackathon 2025 – QPE Challenge

This repository contains our team's submission for the **2025 Korea Quantum Hackathon**, focused on the implementation, analysis, and application of the **Quantum Phase Estimation (QPE)** algorithm.

---

## 📁 Repository Structure

| File/Notebook                               | Description                                                                                                                               |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `problem1.ipynb`                            | QPE implementation for a unitary matrix with known eigenvector; phase estimation for θ = 5/8 and 3/7                                      |
| `qpe.ipynb`                                 | Core implementation of the QPE algorithm used across all problems                                                                         |
| `qpe_analysis.ipynb`                        | Analysis of estimation accuracy vs. number of estimation qubits                                                                           |
| `problem2.ipynb`                            | Estimating eigenvalues of a 4x4 Hermitian matrix using QPE (without prior eigenvector knowledge)                                          |
| `problem3_noise_final.ipynb`                | Noise analysis: QPE under various noise models (e.g., depolarizing, amplitude damping, phase damping, readout error, real IBM Q hardware) |
| `problem3_noise_final_3.ipynb`              | Extended noise model evaluation                                                                                                           |
| `problem4_qpe_with_graph.ipynb`             | QPE-based analysis of estimating ground energy of MAXCUT                                                                                  |
| `problem4_QSVT_with_graph.ipynb`            | QSVT-based Gibbs state preparation + QPE to estimate ground energy (MaxCut)                                                               |
| `problem4_QSVT_clean_simple_code.ipynb`     | Using lower degree of polynomial in QSVT                                                                                                  |
| `problem4_noise_experiment_QSVT+QPE.ipynb`  | Noise experiments on QSVT + QPE combined system                                                                                           |
| `problem4_noise_experiment_only_QSVT.ipynb` | Noise effects isolated to QSVT stage                                                                                                      |

---

## 🧩 Problem Overview and Our Approach

### 1. QPE Implementation
We implemented the Quantum Phase Estimation algorithm for a simple 2x2 unitary matrix:
$U = \begin{bmatrix} 1 & 0 \\ 0 & e^{2\pi i \theta} \end{bmatrix}, \quad v = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$
Estimations were performed for:
- θ = 5/8
- θ = 3/7

We analyzed the accuracy as a function of the number of estimation qubits (see `qpe_analysis.ipynb`).

---

### 2. Estimating Eigenvalues of a Matrix
Given a non-positive-definite 4×4 Hermitian matrix, we estimated all eigenvalues **only** using QPE, without using any classical method to find eigenvectors. The unitary operator was constructed via matrix exponentiation:
$U = e^{2\pi i (I+\frac{M}{\text{norm}})/2}$
We provide its implementation in `problem2.ipynb`.

---

### 3. Noise Sensitivity Analysis
We analyzed QPE performance under:
- Depolarizing noise
- Amplitude damping
- Phase damping
- Readout error
- IBM Q fake real backend
- IBM Q real backend

Our findings (in `problem3_noise_final.ipynb`) highlight how noise models affect phase estimation accuracy.

---

### 4. QPE Application: MaxCut Ground Energy Estimation via QSVT
In this open-ended task, we explored a practical application of QPE:
- We prepared the **Gibbs state** using **Quantum Singular Value Transformation (QSVT)**
- Then applied QPE to estimate the **ground energy** of a MaxCut Hamiltonian

This pipeline demonstrates how QPE can be integrated with advanced quantum techniques to solve combinatorial optimization problems. See:
- `problem4_QSVT_with_graph.ipynb`

We also performed detailed **noise analysis** on this full stack.

---

## 🧠 Key Highlights

- ✅ Full implementation of QPE from scratch (no high-level Qiskit abstractions)
- 📈 Analysis of precision scaling with number of qubits
- 🔬 Realistic noise modeling and impact evaluation
- 💡 Innovative application using **QSVT + QPE** for **MaxCut ground energy estimation**

---

## 📝 References

1. M. A. Nielsen and I. L. Chuang, Quantum computation and
quantum information (Springer, 1999)
1. Thomas G. Wong, Introduction to classical and quantum
computing (Rooted Grove, 2022)
1. L. Lin, Lecture Notes on Quantum Algorithms for Scientific
Computation (https://arxiv.org/abs/2201.08309)

