# Changelog

## 0.0.5

- Fix: Bug in `swap.py`. Added test to cover bug found.

- Fix: Bug in `ppt_distinguishability.py` that prevented checking for higher
  dimensions. Added test to cover bug found.

- Fix: Bug in `ppt_distinguishability.py` that prevented checking 2-dimensional
  cases.

- Fix: Bug in `state_distinguishability.py`. Value returned was being multiplied
  by an unnecessary factor. Added other tests that would have caught this.

- Fix: Bug in `partial_trace.py`. Added test to cover bug found.

- Fix: Bug in `partial_transpose.py` for non-square matrices. Adding test cases to
  cover this previously failing case.
 
- Fix: Bug in `purity.py`. Squaring matrix was using `**2` instead of 
  `np.linalg.matrix_power` 
  
- Fix: Bug in `random_state_vector.py`. Added tests to cover.

- Fix: Bug in `schmidt_rank.py`. Added tests to cover.

- Feature: Added in `symmetric_extension_hierarchy.py`. The function is a
  hierarchy of semidefinite programs that eventually converge to the separable
  value for distinguishing an ensemble of quantum states. The first level is
  just the standard PPT distinguishability probability. Computing higher levels
  of this hierarchy can become intractable quite quickly.

- Feature: Added in ability to perform both minimum-error and unambiguous state
  discrimination in `state_distinguishability.py`. Adding additional tests to
  `test_state_distinguishability.py` to cover this extra feature.
  
- Feature: Added `majorizes.py`; a function to determine whether a vector or matrix
  majorizes another. This is used as a criterion to determine whether a quantum
  state can be converted to another via LOCC. Added `test_majorizes.py` for unit
  testing.

- Feature: Added `perfect_matchings.py`; a function that calculates all the 
  perfect matchings of a given list of objects. Added 
  `test_perfect_matchings.py` for unit testing.

- Feature: Added `breuer.py` under `states/`; a specific bound-entangled state of 
  interest. Added in `test_breuer.py` for unit testing.

- Feature: Added `brauer.py` under `states/`. Added in `test_brauer.py` for unit 
  testing.

- Feature: Added `entanglement_of_formation.py` under `state_props/`. Added in 
  `test_entanglement_of_formation.py` for unit testing.

- Feature: Added `l1_norm_coherence.py` under `state_props/`. Added 
  `test_l1_norm_coherence.py` for unit testing.

- Enhancement: Adding further tests for `symmetric_projection.py`.

- Enhancement: Adding further tests for `ppt_distinguishability.py`.

- Enhancement: Adding further tests for `reduction.py`

- Enhancement: Consolidating `conclusive_state_exclusion.py` and 
  `unambiguous_state_exclusion.py` to just `state_exclusion.py`. Adding in
  optional parameter to specify method of exclusion. Consolidated tests in
  `test_state_exclusion.py`.

## 0.0.6

- Fix: Bug in `symmetric_extension_hierarchy.py` for `level=1` case. Added test
  to cover this bug.
  
 - Feature: Added `in_separable_ball.py` under `state_props/`. Knowing whether a
 density matrix (quantum state) is contained in the separable ball centered at
 the maximally-mixed state is useful for separability testing. Added 
 `test_in_separable_ball.py` for unit testing.

- Feature: Added in ability to perform both minimum-error and unambiguous state
  discrimination in `ppt_distinguishability.py`. Adding additional tests to
  `ppt_state_distinguishability.py` to cover this extra feature.
  
- Feature: Added in ability to compute both primal and dual optimization 
  problems in `ppt_distinguishability.py`. This gives the user the capability
  to obtain the measurement operators and also to use the computationally
  efficiency of the dual problem to make quicker numeric calculations.
 
- Feature: Added `unvec.py` under `matrix_ops/`. This feature is the inverse of
  pre-existing "vec" operation found in `vec.py`. That is, it allows one to take
  a vector and transform it to a (possibly square) matrix.
  
- Feature: Added `choi_to_kraus.py` under `channel_ops/`. This feature allows
  the user to convert a Choi matrix to a list of Kraus operators. This is the 
  inverse of the existing `kraus_to_choi.py` functionality that `toqito` 
  currently offers.

 - Doc-Fix: Trailing `\`` removed in `li_norm_coherence.py`.
 
- Enhancement: Previously ignore tests for `channel_props/` are now being run as
  part of the testing suite.
  
- Enhancement: More robust error checking and adding tolerance arguments for
  various matrix properties found in `matrix_props/`.