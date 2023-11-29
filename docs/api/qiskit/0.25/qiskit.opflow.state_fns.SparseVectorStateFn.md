# qiskit.opflow\.state\_fns.SparseVectorStateFn

<span id="undefined" />

`SparseVectorStateFn(primitive, coeff=1.0, is_measurement=False)`

A class for sparse state functions and measurements in vector representation.

This class uses `scipy.sparse.spmatrix` for the internal representation.

**Parameters**

*   **primitive** (`spmatrix`) – The underlying sparse vector.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the state function.
*   **is\_measurement** (`bool`) – Whether the StateFn is a measurement operator

**Raises**

*   **ValueError** – If the primitive is not a column vector.
*   **ValueError** – If the number of elements in the primitive is not a power of 2.

<span id="undefined" />

`__init__(primitive, coeff=1.0, is_measurement=False)`

**Parameters**

*   **primitive** (`spmatrix`) – The underlying sparse vector.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`]) – A coefficient multiplying the state function.
*   **is\_measurement** (`bool`) – Whether the StateFn is a measurement operator

**Raises**

*   **ValueError** – If the primitive is not a column vector.
*   **ValueError** – If the number of elements in the primitive is not a power of 2.

## Methods

|                                                                                                                                                                    |                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.opflow.state_fns.SparseVectorStateFn.__init__ "qiskit.opflow.state_fns.SparseVectorStateFn.__init__")(primitive\[, coeff, is\_measurement])   | **type primitive**`spmatrix`                                                                                                                                                  |
| [`add`](#qiskit.opflow.state_fns.SparseVectorStateFn.add "qiskit.opflow.state_fns.SparseVectorStateFn.add")(other)                                                 | Return Operator addition of self and other, overloaded by `+`.                                                                                                                |
| [`adjoint`](#qiskit.opflow.state_fns.SparseVectorStateFn.adjoint "qiskit.opflow.state_fns.SparseVectorStateFn.adjoint")()                                          | Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`.                                                                               |
| [`assign_parameters`](#qiskit.opflow.state_fns.SparseVectorStateFn.assign_parameters "qiskit.opflow.state_fns.SparseVectorStateFn.assign_parameters")(param\_dict) | Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another.                                  |
| [`bind_parameters`](#qiskit.opflow.state_fns.SparseVectorStateFn.bind_parameters "qiskit.opflow.state_fns.SparseVectorStateFn.bind_parameters")(param\_dict)       | Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).                             |
| [`compose`](#qiskit.opflow.state_fns.SparseVectorStateFn.compose "qiskit.opflow.state_fns.SparseVectorStateFn.compose")(other\[, permutation, front])              | Composition (Linear algebra-style: A\@B(x) = A(B(x))) is not well defined for states in the binary function model, but is well defined for measurements.                      |
| [`copy`](#qiskit.opflow.state_fns.SparseVectorStateFn.copy "qiskit.opflow.state_fns.SparseVectorStateFn.copy")()                                                   | Return a deep copy of the Operator.                                                                                                                                           |
| [`equals`](#qiskit.opflow.state_fns.SparseVectorStateFn.equals "qiskit.opflow.state_fns.SparseVectorStateFn.equals")(other)                                        | Evaluate Equality between Operators, overloaded by `==`.                                                                                                                      |
| [`eval`](#qiskit.opflow.state_fns.SparseVectorStateFn.eval "qiskit.opflow.state_fns.SparseVectorStateFn.eval")(\[front])                                           | Evaluate the Operator’s underlying function, either on a binary string or another Operator.                                                                                   |
| [`mul`](#qiskit.opflow.state_fns.SparseVectorStateFn.mul "qiskit.opflow.state_fns.SparseVectorStateFn.mul")(scalar)                                                | Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`). |
| [`neg`](#qiskit.opflow.state_fns.SparseVectorStateFn.neg "qiskit.opflow.state_fns.SparseVectorStateFn.neg")()                                                      | Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.                                                                                      |
| [`permute`](#qiskit.opflow.state_fns.SparseVectorStateFn.permute "qiskit.opflow.state_fns.SparseVectorStateFn.permute")(permutation)                               | Permute the qubits of the state function.                                                                                                                                     |
| [`power`](#qiskit.opflow.state_fns.SparseVectorStateFn.power "qiskit.opflow.state_fns.SparseVectorStateFn.power")(exponent)                                        | Compose with Self Multiple Times, undefined for StateFns.                                                                                                                     |
| [`primitive_strings`](#qiskit.opflow.state_fns.SparseVectorStateFn.primitive_strings "qiskit.opflow.state_fns.SparseVectorStateFn.primitive_strings")()            | Return a set of strings describing the primitives contained in the Operator.                                                                                                  |
| [`reduce`](#qiskit.opflow.state_fns.SparseVectorStateFn.reduce "qiskit.opflow.state_fns.SparseVectorStateFn.reduce")()                                             | Try collapsing the Operator structure, usually after some type of conversion, e.g.                                                                                            |
| [`sample`](#qiskit.opflow.state_fns.SparseVectorStateFn.sample "qiskit.opflow.state_fns.SparseVectorStateFn.sample")(\[shots, massive, reverse\_endianness])       | Sample the state function as a normalized probability distribution.                                                                                                           |
| [`tensor`](#qiskit.opflow.state_fns.SparseVectorStateFn.tensor "qiskit.opflow.state_fns.SparseVectorStateFn.tensor")(other)                                        | Return tensor product between self and other, overloaded by `^`.                                                                                                              |
| [`tensorpower`](#qiskit.opflow.state_fns.SparseVectorStateFn.tensorpower "qiskit.opflow.state_fns.SparseVectorStateFn.tensorpower")(other)                         | Return tensor product with self multiple times, overloaded by `^`.                                                                                                            |
| [`to_circuit_op`](#qiskit.opflow.state_fns.SparseVectorStateFn.to_circuit_op "qiskit.opflow.state_fns.SparseVectorStateFn.to_circuit_op")()                        | Convert this state function to a `CircuitStateFn`.                                                                                                                            |
| [`to_density_matrix`](#qiskit.opflow.state_fns.SparseVectorStateFn.to_density_matrix "qiskit.opflow.state_fns.SparseVectorStateFn.to_density_matrix")(\[massive])  | Return matrix representing product of StateFn evaluated on pairs of basis states.                                                                                             |
| [`to_dict_fn`](#qiskit.opflow.state_fns.SparseVectorStateFn.to_dict_fn "qiskit.opflow.state_fns.SparseVectorStateFn.to_dict_fn")()                                 | Convert this state function to a `DictStateFn`.                                                                                                                               |
| [`to_matrix`](#qiskit.opflow.state_fns.SparseVectorStateFn.to_matrix "qiskit.opflow.state_fns.SparseVectorStateFn.to_matrix")(\[massive])                          | Return NumPy representation of the Operator.                                                                                                                                  |
| [`to_matrix_op`](#qiskit.opflow.state_fns.SparseVectorStateFn.to_matrix_op "qiskit.opflow.state_fns.SparseVectorStateFn.to_matrix_op")(\[massive])                 | Return a `VectorStateFn` for this `StateFn`.                                                                                                                                  |
| [`to_spmatrix`](#qiskit.opflow.state_fns.SparseVectorStateFn.to_spmatrix "qiskit.opflow.state_fns.SparseVectorStateFn.to_spmatrix")()                              | Return SciPy sparse matrix representation of the Operator.                                                                                                                    |
| [`traverse`](#qiskit.opflow.state_fns.SparseVectorStateFn.traverse "qiskit.opflow.state_fns.SparseVectorStateFn.traverse")(convert\_fn\[, coeff])                  | Apply the convert\_fn to the internal primitive if the primitive is an Operator (as in the case of `OperatorStateFn`).                                                        |

## Attributes

|                                                                                                                                              |                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `INDENTATION`                                                                                                                                |                                                                            |
| [`coeff`](#qiskit.opflow.state_fns.SparseVectorStateFn.coeff "qiskit.opflow.state_fns.SparseVectorStateFn.coeff")                            | A coefficient by which the state function is multiplied.                   |
| [`instance_id`](#qiskit.opflow.state_fns.SparseVectorStateFn.instance_id "qiskit.opflow.state_fns.SparseVectorStateFn.instance_id")          | Return the unique instance id.                                             |
| [`is_measurement`](#qiskit.opflow.state_fns.SparseVectorStateFn.is_measurement "qiskit.opflow.state_fns.SparseVectorStateFn.is_measurement") | Whether the StateFn object is a measurement Operator.                      |
| [`num_qubits`](#qiskit.opflow.state_fns.SparseVectorStateFn.num_qubits "qiskit.opflow.state_fns.SparseVectorStateFn.num_qubits")             | The number of qubits over which the Operator is defined.                   |
| [`parameters`](#qiskit.opflow.state_fns.SparseVectorStateFn.parameters "qiskit.opflow.state_fns.SparseVectorStateFn.parameters")             | Return a set of Parameter objects contained in the Operator.               |
| [`primitive`](#qiskit.opflow.state_fns.SparseVectorStateFn.primitive "qiskit.opflow.state_fns.SparseVectorStateFn.primitive")                | The primitive which defines the behavior of the underlying State function. |

<span id="undefined" />

`add(other)`

Return Operator addition of self and other, overloaded by `+`.

**Parameters**

**other** (`OperatorBase`) – An `OperatorBase` with the same number of qubits as self, and in the same ‘Operator’, ‘State function’, or ‘Measurement’ category as self (i.e. the same type of underlying function).

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the sum of self and other.

<span id="undefined" />

`adjoint()`

Return a new Operator equal to the Operator’s adjoint (conjugate transpose), overloaded by `~`. For StateFns, this also turns the StateFn into a measurement.

**Return type**

`SparseVectorStateFn`

**Returns**

An `OperatorBase` equivalent to the adjoint of self.

<span id="undefined" />

`assign_parameters(param_dict)`

Binds scalar values to any Terra `Parameters` in the coefficients or primitives of the Operator, or substitutes one `Parameter` for another. This method differs from Terra’s `assign_parameters` in that it also supports lists of values to assign for a give `Parameter`, in which case self will be copied for each parameterization in the binding list(s), and all the copies will be returned in an `OpList`. If lists of parameterizations are used, every `Parameter` in the param\_dict must have the same length list of parameterizations.

**Parameters**

**param\_dict** (`dict`) – The dictionary of `Parameters` to replace, and values or lists of values by which to replace them.

**Return type**

`OperatorBase`

**Returns**

The `OperatorBase` with the `Parameters` in self replaced by the values or `Parameters` in param\_dict. If param\_dict contains parameterization lists, this `OperatorBase` is an `OpList`.

<span id="undefined" />

`bind_parameters(param_dict)`

Same as assign\_parameters, but maintained for consistency with QuantumCircuit in Terra (which has both assign\_parameters and bind\_parameters).

**Return type**

`OperatorBase`

<span id="undefined" />

`property coeff`

A coefficient by which the state function is multiplied.

**Return type**

`Union`\[`complex`, `ParameterExpression`]

<span id="undefined" />

`compose(other, permutation=None, front=False)`

Composition (Linear algebra-style: A\@B(x) = A(B(x))) is not well defined for states in the binary function model, but is well defined for measurements.

**Parameters**

*   **other** (`OperatorBase`) – The Operator to compose with self.
*   **permutation** (`Optional`\[`List`\[`int`]]) – `List[int]` which defines permutation on other operator.
*   **front** (`bool`) – If front==True, return `other.compose(self)`.

**Return type**

`OperatorBase`

**Returns**

An Operator equivalent to the function composition of self and other.

**Raises**

**ValueError** – If self is not a measurement, it cannot be composed from the right.

<span id="undefined" />

`copy()`

Return a deep copy of the Operator.

**Return type**

`OperatorBase`

<span id="undefined" />

`equals(other)`

Evaluate Equality between Operators, overloaded by `==`. Only returns True if self and other are of the same representation (e.g. a DictStateFn and CircuitStateFn will never be equal, even if their vector representations are equal), their underlying primitives are equal (this means for ListOps, OperatorStateFns, or EvolvedOps the equality is evaluated recursively downwards), and their coefficients are equal.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to compare to self.

**Return type**

`bool`

**Returns**

A bool equal to the equality of self and other.

<span id="undefined" />

`eval(front=None)`

Evaluate the Operator’s underlying function, either on a binary string or another Operator. A square binary Operator can be defined as a function taking a binary function to another binary function. This method returns the value of that function for a given StateFn or binary string. For example, `op.eval('0110').eval('1110')` can be seen as querying the Operator’s matrix representation by row 6 and column 14, and will return the complex value at those “indices.” Similarly for a StateFn, `op.eval('1011')` will return the complex value at row 11 of the vector representation of the StateFn, as all StateFns are defined to be evaluated from Zero implicitly (i.e. it is as if `.eval('0000')` is already called implicitly to always “indexing” from column 0).

If `front` is None, the matrix-representation of the operator is returned.

**Parameters**

**front** (`Union`\[`str`, `Dict`\[`str`, `complex`], `ndarray`, `OperatorBase`, `Statevector`, `None`]) – The bitstring, dict of bitstrings (with values being coefficients), or StateFn to evaluated by the Operator’s underlying function, or None.

**Return type**

`Union`\[`OperatorBase`, `complex`]

**Returns**

The output of the Operator’s evaluation function. If self is a `StateFn`, the result is a float or complex. If self is an Operator (`PrimitiveOp, ComposedOp, SummedOp, EvolvedOp,` etc.), the result is a StateFn. If `front` is None, the matrix-representation of the operator is returned, which is a `MatrixOp` for the operators and a `VectorStateFn` for state-functions. If either self or front contain proper `ListOps` (not ListOp subclasses), the result is an n-dimensional list of complex or StateFn results, resulting from the recursive evaluation by each OperatorBase in the ListOps.

<span id="undefined" />

`property instance_id`

Return the unique instance id.

**Return type**

`int`

<span id="undefined" />

`property is_measurement`

Whether the StateFn object is a measurement Operator.

**Return type**

`bool`

<span id="undefined" />

`mul(scalar)`

Returns the scalar multiplication of the Operator, overloaded by `*`, including support for Terra’s `Parameters`, which can be bound to values later (via `bind_parameters`).

**Parameters**

**scalar** (`Union`\[`complex`, `ParameterExpression`]) – The real or complex scalar by which to multiply the Operator, or the `ParameterExpression` to serve as a placeholder for a scalar factor.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to product of self and scalar.

<span id="undefined" />

`neg()`

Return the Operator’s negation, effectively just multiplying by -1.0, overloaded by `-`.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the negation of self.

<span id="undefined" />

`property num_qubits`

The number of qubits over which the Operator is defined. If `op.num_qubits == 5`, then `op.eval('1' * 5)` will be valid, but `op.eval('11')` will not.

**Return type**

`int`

**Returns**

The number of qubits accepted by the Operator’s underlying function.

<span id="undefined" />

`property parameters`

Return a set of Parameter objects contained in the Operator.

<span id="undefined" />

`permute(permutation)`

Permute the qubits of the state function.

**Parameters**

**permutation** (`List`\[`int`]) – A list defining where each qubit should be permuted. The qubit at index j of the circuit should be permuted to position permutation\[j].

**Return type**

`OperatorBase`

**Returns**

A new StateFn containing the permuted primitive.

<span id="undefined" />

`power(exponent)`

Compose with Self Multiple Times, undefined for StateFns.

**Parameters**

**exponent** (`int`) – The number of times to compose self with self.

**Raises**

**ValueError** – This function is not defined for StateFns.

**Return type**

`OperatorBase`

<span id="undefined" />

`property primitive`

The primitive which defines the behavior of the underlying State function.

<span id="undefined" />

`primitive_strings()`

Return a set of strings describing the primitives contained in the Operator. For example, `{'QuantumCircuit', 'Pauli'}`. For hierarchical Operators, such as `ListOps`, this can help illuminate the primitives represented in the various recursive levels, and therefore which conversions can be applied.

**Return type**

`Set`\[`str`]

**Returns**

A set of strings describing the primitives contained within the Operator.

<span id="undefined" />

`reduce()`

Try collapsing the Operator structure, usually after some type of conversion, e.g. trying to add Operators in a SummedOp or delete needless IGates in a CircuitOp. If no reduction is available, just returns self.

**Return type**

`OperatorBase`

**Returns**

The reduced `OperatorBase`.

<span id="undefined" />

`sample(shots=1024, massive=False, reverse_endianness=False)`

Sample the state function as a normalized probability distribution. Returns dict of bitstrings in order of probability, with values being probability.

**Parameters**

*   **shots** (`int`) – The number of samples to take to approximate the State function.
*   **massive** (`bool`) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.
*   **reverse\_endianness** (`bool`) – Whether to reverse the endianness of the bitstrings in the return dict to match Terra’s big-endianness.

**Return type**

`dict`

**Returns**

A dict containing pairs sampled strings from the State function and sampling frequency divided by shots.

<span id="undefined" />

`tensor(other)`

Return tensor product between self and other, overloaded by `^`. Note: You must be conscious of Qiskit’s big-endian bit printing convention. Meaning, Plus.tensor(Zero) produces a |+⟩ on qubit 0 and a |0⟩ on qubit 1, or |+⟩⨂|0⟩, but would produce a QuantumCircuit like

> |0⟩– |+⟩–

Because Terra prints circuits and results with qubit 0 at the end of the string or circuit.

**Parameters**

**other** (`OperatorBase`) – The `OperatorBase` to tensor product with self.

**Return type**

`OperatorBase`

**Returns**

An `OperatorBase` equivalent to the tensor product of self and other.

<span id="undefined" />

`tensorpower(other)`

Return tensor product with self multiple times, overloaded by `^`.

**Parameters**

**other** (`int`) – The int number of times to tensor product self with itself via `tensorpower`.

**Return type**

`Union`\[`OperatorBase`, `int`]

**Returns**

An `OperatorBase` equivalent to the tensorpower of self by other.

<span id="undefined" />

`to_circuit_op()`

Convert this state function to a `CircuitStateFn`.

**Return type**

`OperatorBase`

<span id="undefined" />

`to_density_matrix(massive=False)`

Return matrix representing product of StateFn evaluated on pairs of basis states. Overridden by child classes.

**Parameters**

**massive** (`bool`) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.

**Return type**

`ndarray`

**Returns**

The NumPy array representing the density matrix of the State function.

**Raises**

**ValueError** – If massive is set to False, and exponentially large computation is needed.

<span id="undefined" />

`to_dict_fn()`

Convert this state function to a `DictStateFn`.

**Return type**

`StateFn`

**Returns**

A new DictStateFn equivalent to `self`.

<span id="undefined" />

`to_matrix(massive=False)`

Return NumPy representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings. Warn if more than 16 qubits to force having to set `massive=True` if such a large vector is desired.

**Return type**

`ndarray`

**Returns**

The NumPy `ndarray` equivalent to this Operator.

<span id="undefined" />

`to_matrix_op(massive=False)`

Return a `VectorStateFn` for this `StateFn`.

**Parameters**

**massive** (`bool`) – Whether to allow large conversions, e.g. creating a matrix representing over 16 qubits.

**Return type**

`OperatorBase`

**Returns**

A VectorStateFn equivalent to self.

<span id="undefined" />

`to_spmatrix()`

Return SciPy sparse matrix representation of the Operator. Represents the evaluation of the Operator’s underlying function on every combination of basis binary strings.

**Return type**

`OperatorBase`

**Returns**

The SciPy `spmatrix` equivalent to this Operator.

<span id="undefined" />

`traverse(convert_fn, coeff=None)`

Apply the convert\_fn to the internal primitive if the primitive is an Operator (as in the case of `OperatorStateFn`). Otherwise do nothing. Used by converters.

**Parameters**

*   **convert\_fn** (`Callable`) – The function to apply to the internal OperatorBase.
*   **coeff** (`Union`\[`complex`, `ParameterExpression`, `None`]) – A coefficient to multiply by after applying convert\_fn. If it is None, self.coeff is used instead.

**Return type**

`OperatorBase`

**Returns**

The converted StateFn.