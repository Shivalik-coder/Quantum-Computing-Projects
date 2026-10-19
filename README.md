# Quantum Computing Projects

## Overview

This repository contains a collection of quantum computing projects, experiments, and implementations developed using Python, Qiskit, and related quantum computing tools.

The projects explore quantum computing concepts through practical circuit implementations, simulations, mathematical explanations, and visualizations.

Each project is organized into a separate directory with its own Jupyter Notebook, documentation, and required dependencies.

The repository will continue to expand with additional implementations covering various quantum computing concepts, algorithms, and applications.

---

## Technologies & Tools

| Technology | Purpose |
|---|---|
| Python | Quantum programming and implementation |
| Qiskit | Quantum circuit design and execution |
| Qiskit Aer | Quantum circuit simulation |
| Jupyter Notebook | Interactive development and documentation |
| Matplotlib | Circuit visualization and result analysis |
| pylatexenc | Mathematical expression rendering |

---

## Project Directory

| Project | Description | Documentation |
|---|---|---|
| 01 — Treasure Door | Quantum circuit implementation of the classic Two Guardians Riddle using superposition, entanglement, and quantum logic gates. | [View Project](./01-treasure-door/) |

Additional projects will be added as the repository expands.

---

## Repository Structure

```text
Quantum-Computing-Projects/
│
├── README.md
│
└── 01-treasure-door/
    ├── README.md
    ├── The treasure door.ipynb
    └── requirements.txt
```

Each project directory contains:

- **Jupyter Notebook (`.ipynb`)** — Quantum circuit implementations, explanations, and experimental results.
- **README.md** — Project overview, methodology, implementation steps, and observations.
- **requirements.txt** — Python libraries required to run the project.

---

## Featured Project

### 01 — The Two Guardians Riddle with Qiskit

This project explores how a classical logical problem can be represented using quantum circuits.

The Two Guardians Riddle involves two doors, one containing a treasure, and two guardians: one who always tells the truth and another who always lies.

The objective is to determine the treasure's location by asking only one question.

The implementation uses a three-qubit quantum circuit to represent the logical relationships between the treasure location and the guardians' behavior.

**Quantum concepts explored:**

- Quantum superposition
- Quantum entanglement
- Hadamard gates
- Controlled-NOT (CNOT) gates
- Pauli-X gates
- SWAP gates
- Quantum measurement
- Quantum circuit simulation

**Project resources:**

- [Project Documentation](./01-treasure-door/README.md)
- [Jupyter Notebook — The treasure door.ipynb](./01-treasure-door/The%20treasure%20door.ipynb)
- [Python Dependencies](./01-treasure-door/requirements.txt)

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Shivalik-coder/Quantum-Computing-Projects.git
```

Navigate into the repository:

```bash
cd Quantum-Computing-Projects
```

### 2. Create a Python Virtual Environment

Using Python 3.13:

```bash
python3.13 -m venv .venv
```

Activate the environment on macOS:

```bash
source .venv/bin/activate
```

### 3. Install Project Dependencies

For the Treasure Door project:

```bash
python -m pip install -r 01-treasure-door/requirements.txt
```

If Jupyter Notebook is not installed:

```bash
python -m pip install notebook
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Navigate to the desired project directory and open its Jupyter Notebook.

For Treasure Door, open:

`01-treasure-door/The treasure door.ipynb`

Run the notebook cells in their intended order to explore the quantum circuit implementation.

---

## Areas of Exploration

The repository focuses on practical implementations and experiments involving:

- Quantum computing fundamentals
- Quantum circuit design
- Quantum logic gates
- Superposition and entanglement
- Quantum algorithms
- Quantum simulation
- Quantum measurement and probability
- Mathematical representations of quantum systems

Additional topics and implementations may be introduced in future projects.

---

## Repository Organization

Projects follow a numbered directory structure:

```text
01-project-name/
02-project-name/
03-project-name/
...
```

This convention provides a consistent way to organize individual implementations and their supporting documentation.

Each project is maintained independently to make its code, methodology, and results easier to navigate.

---

## Conclusion

This repository documents practical explorations of quantum computing through Python-based implementations, circuit simulations, and technical explanations.

The goal is to develop and demonstrate an understanding of quantum computing principles by applying theoretical concepts to executable experiments.

The repository will be updated as additional quantum computing projects are developed.
