---
title: dagcircuit
description: API reference for qiskit.dagcircuit
in_page_toc_min_heading_level: 1
python_api_type: module
python_api_name: qiskit.dagcircuit
---

<span id="module-qiskit.dagcircuit" />

<span id="qiskit-dagcircuit" />

# DAG Circuits

<span id="module-qiskit.dagcircuit" />

`qiskit.dagcircuit`

## DAG Circuits

|                                                                                                                                              |                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [`DAGCircuit`](qiskit.dagcircuit.DAGCircuit#qiskit.dagcircuit.DAGCircuit "qiskit.dagcircuit.DAGCircuit")()                                   | Quantum circuit as a directed acyclic graph.                                                       |
| [`DAGNode`](qiskit.dagcircuit.DAGNode#qiskit.dagcircuit.DAGNode "qiskit.dagcircuit.DAGNode")(\[type, op, name, qargs, cargs, …])             | Object to represent the information at a node in the DAGCircuit.                                   |
| [`DAGDepNode`](qiskit.dagcircuit.DAGDepNode#qiskit.dagcircuit.DAGDepNode "qiskit.dagcircuit.DAGDepNode")(\[type, op, name, qargs, cargs, …]) | Object to represent the information at a node in the DAGDependency().                              |
| [`DAGDependency`](qiskit.dagcircuit.DAGDependency#qiskit.dagcircuit.DAGDependency "qiskit.dagcircuit.DAGDependency")()                       | Object to represent a quantum circuit as a directed acyclic graph via operation dependencies (i.e. |

## Exceptions

|                                                                                                                                     |                                                        |
| ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| [`DAGCircuitError`](qiskit.dagcircuit.DAGCircuitError#qiskit.dagcircuit.DAGCircuitError "qiskit.dagcircuit.DAGCircuitError")(\*msg) | Base class for errors raised by the DAGCircuit object. |
