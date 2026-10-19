# The Two Guardians Riddle with Qiskit

## Project Overview

**Treasure Door** is a quantum computing project developed using Python, Qiskit, and Jupyter Notebook.

The project explores how quantum circuits can represent and simulate the logical relationships behind the classic **Two Guardians Riddle**.

The riddle involves two doors and two guardians:

- One door contains a treasure.
- One guardian always tells the truth.
- The other guardian always lies.
- Both guardians know where the treasure is.
- Only one question can be asked to one guardian.

The challenge is to determine which door contains the treasure.

The logical solution is to ask either guardian:

> **"Which door would the other guardian tell me not to open?"**

Both guardians will indicate the treasure door.

This project demonstrates the riddle through a simplified three-qubit quantum circuit, using superposition, entanglement, controlled quantum gates, and measurement.

---

## Project Objectives

The main objectives of this project are to:

1. Understand how classical logical problems can be represented using quantum circuits.
2. Explore quantum superposition and entanglement.
3. Implement quantum logic using Qiskit.
4. Understand the operations of Hadamard, CNOT, Pauli-X, and SWAP gates.
5. Simulate the truth-telling and lying behavior of the two guardians.
6. Perform quantum measurements and analyze the resulting probabilities.
7. Visualize quantum circuits and simulation results.

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Python 3.13 | Programming language |
| Qiskit | Quantum circuit construction |
| Qiskit Aer | Quantum circuit simulation |
| Jupyter Notebook | Interactive implementation and documentation |
| Matplotlib | Quantum circuit and result visualization |
| pylatexenc | Mathematical label rendering in circuit diagrams |

---

## Quantum Circuit Representation

The circuit uses **three qubits and three classical bits**.

| Qubit | Representation |
|---|---|
| q0 | Treasure location / first answer register |
| q1 | Guardian's answer / second answer register |
| q2 | Identity of the lying guardian |

The following convention is used:

- **q2 = 0:** Guardian 0 lies, and Guardian 1 tells the truth.
- **q2 = 1:** Guardian 1 lies, and Guardian 0 tells the truth.

The circuit applies quantum gates to represent the relationships between these three variables.

---

## Project Implementation

The notebook develops the quantum circuit step by step.

### Step 1 — Creating the Treasure Position

A Hadamard gate is applied to q0, creating a superposition of both possible treasure locations.

This represents the initial uncertainty about which door contains the treasure.

### Step 2 — Making Both Guardians Know the Treasure Location

A Controlled-NOT (CNOT) gate is applied with q0 as the control and q1 as the target.

This correlates q1 with the treasure-location qubit and creates an entangled state.

### Step 3 — Randomly Choosing the Lying Guardian

A Hadamard gate is applied to q2.

This introduces superposition representing the two possibilities:

- Guardian 0 is lying.
- Guardian 1 is lying.

At this stage, the system represents four possible combinations of treasure locations and lying guardians.

### Step 4 — Introducing the Lying Behavior

Controlled quantum operations represent the behavior of each guardian.

- A CNOT gate flips q1 when Guardian 1 is designated as the liar.
- An X-CNOT-X sequence flips q0 when Guardian 0 is designated as the liar.

These operations encode the truth-telling and lying conditions established in the riddle.

### Step 5 — Asking the Question

The circuit models the question:

**"Which door would the other guardian tell me not to open?"**

This step contains three operations:

**Step 5.1 — SWAP Gate**

Exchanges the two answer registers to represent asking about the other guardian.

**Step 5.2 — Pauli-X Gates**

Inverts the answers to represent the phrase "not to open."

**Step 5.3 — Applying the Lying Behavior Again**

Reapplies the controlled lying operations to account for the possibility that the guardian being questioned is also the liar.

The final circuit produces matching answer-register values in every represented scenario.

### Step 6 — Measuring the Quantum Circuit

All three qubits are measured and their values are stored in classical bits.

The completed circuit is designed to run using Qiskit Aer with **1,024 simulation shots**.

The measurement results can then be displayed as frequencies and visualized using a histogram.

---

## Expected Results

The final quantum state before measurement, using the notebook's mathematical bit-ordering convention, is:

$$
|\psi\rangle =
\frac{|000\rangle + |001\rangle + |110\rangle + |111\rangle}{2}
$$

Each basis state has a theoretical probability of **25%**.

Because Qiskit displays measured bit strings in the order `c2 c1 c0`, the expected simulation outcomes are:

| Qiskit Output | Expected Probability |
|---|---|
| `000` | 25% |
| `100` | 25% |
| `011` | 25% |
| `111` | 25% |

With 1,024 shots, approximately 256 occurrences of each outcome are expected.

Actual frequencies can vary because quantum measurement is probabilistic.

### Key Observation

The important relationship demonstrated by the circuit is:

**q0 = q1**

Both answer registers agree regardless of which guardian is designated as the liar.

The circuit therefore reproduces a central logical property of the Two Guardians Riddle within the simplified quantum model.

**Note:** This experiment does not discover a separately predetermined hidden treasure location. It represents possible scenarios and demonstrates that the final answer remains consistent with the treasure-location bit in each scenario.

---

## Installation and Setup

### 1. Requirements

- Python 3.13
- Jupyter Notebook
- Qiskit
- Qiskit Aer
- Matplotlib
- pylatexenc

### 2. Create a Virtual Environment

```bash
python3.13 -m venv .venv
```

Activate the environment on macOS:

```bash
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
python -m pip install qiskit qiskit-aer matplotlib pylatexenc ipykernel
```

If Jupyter Notebook is not already installed:

```bash
python -m pip install notebook
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

`The treasure door.ipynb`

Select the Python environment containing the installed dependencies.

Run the notebook cells in their intended order.

**Execution note:** The notebook version originally provided includes an incomplete code cell containing `pip ins`. This is not valid Python and should be skipped. Its saved simulator output also reflects an earlier missing-dependency error; simulation results need to be regenerated in the configured environment.

---

## Project Structure

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

The `requirements.txt` file can be added to record the dependencies for this project.

---

## Learning Outcomes

Through this project, I explored:

- How to create quantum circuits using Qiskit.
- How Hadamard gates represent multiple possibilities through superposition.
- How CNOT gates create correlations and entanglement.
- How controlled operations can represent conditional logical behavior.
- How Pauli-X and SWAP gates transform quantum states.
- How quantum measurement converts quantum information into classical results.
- How to interpret quantum measurement probabilities and simulation outputs.
- How to combine classical logic and quantum computing concepts in a practical learning project.

---

## Conclusion

The Treasure Door project demonstrates how a classical logic riddle can be modeled through a sequence of quantum gate operations.

The main result is that the final answer registers agree regardless of which guardian is lying.

This project serves as an introduction to quantum circuit design, quantum logic, simulation, and measurement using Qiskit.

It forms part of an ongoing exploration of quantum computing.

---

## Project Notebook

[View The treasure door.ipynb](https://github.com/Shivalik-coder/Quantum-Computing-Projects/blob/main/01-treasure-door/The%20treasure%20door.ipynb)
