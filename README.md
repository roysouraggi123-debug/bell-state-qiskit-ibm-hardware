# Bell State Simulation and Execution on IBM Quantum Hardware

A two-qubit Bell-state experiment using **Qiskit**, **Qiskit Aer**, and the **IBM Quantum Platform**. The circuit is first simulated locally and then executed on a real IBM quantum processor.

## 1. Project Overview

The Bell state is one of the simplest examples of quantum entanglement. In this project, a two-qubit Bell state is prepared using a Hadamard gate followed by a CNOT gate.

The circuit is simulated locally using Qiskit Aer. The same circuit is subsequently executed on real quantum hardware through the IBM Quantum Platform.

The measurement outcomes from the ideal simulator and the actual quantum processor are compared to examine the effects of imperfections in real quantum hardware.

## 2. Objectives

- Construct a two-qubit Bell-state circuit using Qiskit.
- Simulate the circuit using Qiskit Aer.
- Connect to the IBM Quantum Platform.
- Transpile the circuit for an actual quantum processor.
- Execute the circuit on IBM quantum hardware.
- Compare ideal simulation results with hardware measurements.

## 3. Experimental Methodology

The experiment consists of two stages:

**Stage 1: Local simulation**

The Bell-state circuit is simulated using Qiskit Aer with 1024 measurement shots.

**Stage 2: Real quantum hardware execution**

The same circuit is transpiled for an operational IBM quantum processor and submitted using Qiskit IBM Runtime.

The selected backend was `ibm_marrakesh`, which has 156 qubits.

The theoretical background and step-by-step mathematical derivation are provided in the Jupyter notebook.

## 4. Local Simulation Results

The local Aer simulation produced the following measurement counts:

| Measurement |   Counts |
| ----------- | -------: |
| 00          |      514 |
| 11          |      510 |
| **Total**   | **1024** |

Only the outcomes 00 and 11 were obtained, with nearly equal frequencies. This agrees with the expected behaviour of an ideal Bell-state circuit.

## 5. IBM Quantum Hardware Results

The circuit was executed on the IBM Marrakesh quantum processor using 1024 shots.

**Backend:** `ibm_marrakesh`

**Job ID:** `dbqan7ok09pc73astnc0`

The observed measurement counts were:

| Measurement |   Counts | Percentage |
| ----------- | -------: | ---------: |
| 00          |      525 |     51.27% |
| 01          |       30 |      2.93% |
| 10          |       15 |      1.46% |
| 11          |      454 |     44.34% |
| **Total**   | **1024** |   **100%** |

The outcomes 00 and 11 together account for 95.61% of the measurements. The remaining 4.39% correspond to 01 and 10.

Unlike the ideal simulator, real quantum hardware is affected by imperfections in gate operations, decoherence and measurement. These effects can produce outcomes that are not expected in the ideal circuit.

The results show strong correlations between the measurement outcomes of the two qubits. However, measurements in the computational basis alone do not establish the fidelity of the prepared Bell state.

## 6. Simulation and Hardware Comparison

The local simulator produced only 00 and 11, with nearly equal frequencies.

The IBM quantum processor also produced 00 and 11 as the dominant outcomes, but a small number of 01 and 10 outcomes were observed.

This difference illustrates the effects of imperfections in real quantum hardware.

## 7. Software and Tools

- Python 3.11
- Qiskit 2.6.2
- Qiskit Aer 0.18.2
- Qiskit IBM Runtime 0.52.0
- Matplotlib 3.11.2
- IBM Quantum Platform
- IBM Marrakesh quantum processor

## 8. Installation and Execution

Clone the repository:

```bash
git clone https://github.com/roysouraggi123-debug/bell-state-qiskit-ibm-hardware.git
```

Move into the project directory:

```bash
cd bell-state-qiskit-ibm-hardware
```

Install the required packages:

```bash
pip install qiskit==2.6.2
pip install qiskit-aer==0.18.2
pip install qiskit-ibm-runtime==0.52.0
pip install matplotlib==3.11.2
```

Open the Jupyter notebook:

```bash
jupyter notebook Bell_State_IBM_Quantum.ipynb
```

### IBM Quantum Account Configuration

To execute the circuit on real IBM quantum hardware, users must have their own IBM Quantum account and configure their credentials locally.

The public notebook uses:

```python
from qiskit_ibm_runtime import QiskitRuntimeService

service = QiskitRuntimeService()
```

Configure your own IBM Quantum credentials separately before running the hardware execution cells. **Never publish your API key or private credentials in the notebook or repository.**

## 9. Conclusion

In this experiment, a two-qubit Bell state was successfully prepared and simulated using Qiskit Aer. The same circuit was subsequently executed on the IBM Marrakesh quantum processor.

The ideal simulation produced only the outcomes 00 and 11, with nearly equal frequencies. The real hardware experiment also showed these two outcomes as the dominant measurement results, but a small number of 01 and 10 outcomes were observed.

The difference between the two results illustrates the effect of imperfections in real quantum hardware.

This project provides a practical introduction to quantum circuit construction, local simulation, hardware-specific transpilation and execution on a real quantum processor.

---

**Author:** Souraggi Roy

**Repository:** [Bell State Simulation and IBM Quantum Hardware](https://github.com/roysouraggi123-debug/bell-state-qiskit-ibm-hardware)

