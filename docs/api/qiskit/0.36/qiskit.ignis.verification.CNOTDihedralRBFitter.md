---
title: CNOTDihedralRBFitter
description: API reference for qiskit.ignis.verification.CNOTDihedralRBFitter
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.ignis.verification.CNOTDihedralRBFitter
---

# CNOTDihedralRBFitter

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter" />

`CNOTDihedralRBFitter(cnotdihedral_Z_result, cnotdihedral_X_result, elmnts_lengths, rb_pattern=None)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Bases: `qiskit.ignis.verification.randomized_benchmarking.fitters.RBFitterBase`

Class for fitters for non-Clifford CNOT-Dihedral RB.

Derived from RBFitterBase class. Contains two RBFitter objects.

**Parameters**

*   **cnotdihedral\_Z\_result** (*qiskit.Result*) – list of results of the RB sequence that measures the ground state.
*   **cnotdihedral\_X\_result** (*qiskit.Result*) – list of results of the RB sequence that measures the $|+...+>$ state.
*   **elmnts\_lengths** (*list*) – the group elements lengths, 2D list i x j where i is the number of patterns, j is the number of elements lengths.
*   **rb\_pattern** (*list*) – the pattern for the RB sequences.

## Methods

### add\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.add_data" />

`CNOTDihedralRBFitter.add_data(new_cnotdihedral_Z_result, new_cnotdihedral_X_result, rerun_fit=True)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Add a new result.

**Parameters**

*   **new\_cnotdihedral\_Z\_result** (*list*) – list of rb results of the cnot-dihedral Z circuits.
*   **new\_cnotdihedral\_X\_result** (*list*) – list of rb results of the cnot-dihedral X circuits.
*   **rerun\_fit** (*bool*) – re-calculate the means and fit the result.

#### Additional information:

Assumes that the executed ‘result’ is the output of circuits generated by randomized\_benchmarking\_seq.

### calc\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.calc_data" />

`CNOTDihedralRBFitter.calc_data()`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Retrieve probabilities of success from execution results. Outputs results into an internal variable: \_raw\_data .

### calc\_statistics

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.calc_statistics" />

`CNOTDihedralRBFitter.calc_statistics()`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Extract averages and std dev. Outputs results into an internal variable: \_ydata .

### fit\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data" />

`CNOTDihedralRBFitter.fit_data()`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Fit the non-Clifford cnot-dihedral RB results.

Fit each of the patterns. According to the paper:

[Scalable randomized benchmarking of non-Clifford gates](https://www.nature.com/articles/npjqi201612)

**Returns**

A list of dictionaries where each dictionary corresponds to a pattern and has fields:

> *   `alpha` - alpha parameter of the non-Clifford cnot-dihedral RB.
> *   `'alpha_err` - the error of the alpha parameter of the non-Clifford cnot-dihedral RB.
> *   `epg_est` - the estimated error per a CNOT-dihedral element.
> *   `epg_est_error` - the estimated error derived from the params\_err.

**Return type**

list

### fit\_data\_pattern

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit_data_pattern" />

`CNOTDihedralRBFitter.fit_data_pattern(patt_ind, fit_guess, fit_index=0)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Fit the RB results of a particular pattern to an exponential curve.

**Parameters**

*   **patt\_ind** (*int*) – index of the data pattern to fit.
*   **fit\_guess** (*list*) – guess values for the fit.
*   **fit\_index** (*int*) – 0 fit the standard data, 1 fit the interleaved data.

### plot\_rb\_data

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.plot_rb_data" />

`CNOTDihedralRBFitter.plot_rb_data(pattern_index=0, ax=None, add_label=True, show_plt=True)`[GitHub](https://github.com/qiskit-community/qiskit-ignis/tree/stable/0.7/qiskit/ignis/verification/randomized_benchmarking/fitters.py "view source code")

Plot non-Clifford cnot-dihedral randomized benchmarking data of a single pattern.

**Parameters**

*   **pattern\_index** (*int*) – which RB pattern to plot.
*   **ax** (*Axes*) – plot axis (if passed in).
*   **add\_label** (*bool*) – Add an EPG label.
*   **show\_plt** (*bool*) – display the plot.

**Raises**

**ImportError** – if matplotlib is not installed.

## Attributes

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.cliff_lengths" />

### cliff\_lengths

Return group elements lengths.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit" />

### fit

Return fit as a 2 element list.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.fit_cnotdihedral" />

### fit\_cnotdihedral

Return cnotdihedral fit parameters.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.raw_data" />

### raw\_data

Return raw\_data as 2 element list.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.rb_fit_fun" />

### rb\_fit\_fun

Return the fit function rb\_fit\_fun.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_X" />

### rbfit\_X

Return the cnotdihedral X fitter.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.rbfit_Z" />

### rbfit\_Z

Return the cnotdihedral Z fitter.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.results" />

### results

Return all the results as a 2 element list.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.seeds" />

### seeds

Return the number of loaded seeds as a 2 element list.

<span id="qiskit.ignis.verification.CNOTDihedralRBFitter.ydata" />

### ydata

Return ydata (means and std devs) as a 2 element list.
