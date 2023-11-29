---
title: MatrixFunctional
description: API reference for qiskit.algorithms.linear_solvers.MatrixFunctional
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.linear_solvers.MatrixFunctional
---

# MatrixFunctional[¶](#matrixfunctional "Permalink to this headline")

<span id="qiskit.algorithms.linear_solvers.MatrixFunctional" />

`MatrixFunctional(main_diag, off_diag)`

Bases: [`qiskit.algorithms.linear_solvers.observables.linear_system_observable.LinearSystemObservable`](qiskit.algorithms.linear_solvers.LinearSystemObservable "qiskit.algorithms.linear_solvers.observables.linear_system_observable.LinearSystemObservable")

The deprecated class for the matrix functional of the vector solution to the linear systems.

Examples:

```python
import warnings
import numpy as np
from qiskit import QuantumCircuit
from qiskit.algorithms.linear_solvers.observables.matrix_functional import             MatrixFunctional
from qiskit.transpiler.passes import RemoveResetInZeroState
from qiskit.opflow import StateFn

tpass = RemoveResetInZeroState()

vector = [1.0, -2.1, 3.2, -4.3]
with warnings.catch_warnings():
    warnings.simplefilter('ignore')
    observable = MatrixFunctional(1, -1 / 3)

init_state = vector / np.linalg.norm(vector)
num_qubits = int(np.log2(len(vector)))

# Get observable circuits
obs_circuits = observable.observable_circuit(num_qubits)
qcs = []
for obs_circ in obs_circuits:
    qc = QuantumCircuit(num_qubits)
    qc.isometry(init_state, list(range(num_qubits)), None)
    qc.append(obs_circ, list(range(num_qubits)))
    qcs.append(tpass(qc.decompose()))

# Get observables
observable_ops = observable.observable(num_qubits)
state_vecs = []
# First is the norm
state_vecs.append((~StateFn(observable_ops[0]) @ StateFn(qcs[0])).eval())
for i in range(1, len(observable_ops), 2):
    state_vecs += [(~StateFn(observable_ops[i]) @ StateFn(qcs[i])).eval(),
                   (~StateFn(observable_ops[i + 1]) @ StateFn(qcs[i + 1])).eval()]

# Obtain result
result = observable.post_processing(state_vecs, num_qubits)

# Obtain analytical evaluation
exact = observable.evaluate_classically(init_state)
```

**Parameters**

*   **main\_diag** (`float`) – The main diagonal of the tridiagonal Toeplitz symmetric matrix to compute the functional.
*   **off\_diag** (`int`) – The off diagonal of the tridiagonal Toeplitz symmetric matrix to compute the functional.

## Methods

### evaluate\_classically

<span id="qiskit.algorithms.linear_solvers.MatrixFunctional.evaluate_classically" />

`MatrixFunctional.evaluate_classically(solution)`

Evaluates the given observable on the solution to the linear system.

**Parameters**

**solution** (`Union`\[`array`, [`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]) – The solution to the system as a numpy array or the circuit that prepares it.

**Return type**

`float`

**Returns**

The value of the observable.

### observable

<span id="qiskit.algorithms.linear_solvers.MatrixFunctional.observable" />

`MatrixFunctional.observable(num_qubits)`

The observable operators.

**Parameters**

**num\_qubits** (`int`) – The number of qubits on which the observable will be applied.

**Return type**

`Union`\[[`TensoredOp`](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp"), `List`\[[`TensoredOp`](qiskit.opflow.list_ops.TensoredOp "qiskit.opflow.list_ops.tensored_op.TensoredOp")]]

**Returns**

The observable as a list of sums of Pauli strings.

### observable\_circuit

<span id="qiskit.algorithms.linear_solvers.MatrixFunctional.observable_circuit" />

`MatrixFunctional.observable_circuit(num_qubits)`

The circuits to implement the matrix functional observable.

**Parameters**

**num\_qubits** (`int`) – The number of qubits on which the observable will be applied.

**Return type**

`Union`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit"), `List`\[[`QuantumCircuit`](qiskit.circuit.QuantumCircuit "qiskit.circuit.quantumcircuit.QuantumCircuit")]]

**Returns**

The observable as a list of QuantumCircuits.

### post\_processing

<span id="qiskit.algorithms.linear_solvers.MatrixFunctional.post_processing" />

`MatrixFunctional.post_processing(solution, num_qubits, scaling=1)`

Evaluates the matrix functional on the solution to the linear system.

**Parameters**

*   **solution** (`Union`\[`float`, `List`\[`float`]]) – The list of probabilities calculated from the circuit and the observable.
*   **num\_qubits** (`int`) – The number of qubits where the observable was applied.
*   **scaling** (`float`) – Scaling of the solution.

**Return type**

`float`

**Returns**

The value of the absolute average.

**Raises**

**ValueError** – If the input is not in the correct format.
