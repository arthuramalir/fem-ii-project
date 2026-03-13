# fem-ii-project

## Project Ideas

This repository collects and synthesizes candidate research directions for the FEM II project. The ideas span stochastic optimization, uncertainty quantification for PDEs, and hybrid inverse problems.

---

### 1. Random Walk Models of Stochastic Optimization in Multimodal Landscapes

**Working title:** *Random Walk Models of Stochastic Optimization in Multimodal Landscapes*

Investigate how random-walk-based optimization algorithms (e.g. simulated annealing, stochastic gradient descent with noise, Langevin dynamics) navigate objective functions that possess many local minima. Key questions include:
- How does the geometry of the loss landscape (barrier heights, basin widths) affect convergence rates?
- Can Markov-chain analysis of the random walk yield sharp complexity bounds?
- What role does noise temperature / step-size annealing play in escaping local traps?

---

### 2. Multilevel Monte-Carlo / Polynomial Chaos for Stochastic PDEs

Two complementary directions for quantifying uncertainty in PDE models:

#### Option A — Multilevel Monte-Carlo (MLMC)
**Working title:** *Multilevel Monte-Carlo Estimation for Stochastic Elliptic PDEs: Algorithms and Complexity Analysis*

Apply the MLMC hierarchy to elliptic PDEs with random coefficients (e.g. random permeability fields). Goals:
- Derive optimal level-selection and sample-allocation strategies.
- Prove complexity estimates (cost vs. mean-square error) for finite-element discretizations.
- Benchmark against single-level MC and quasi-MC alternatives.

#### Option B — Spectral Polynomial Chaos
**Working title:** *Spectral Polynomial Chaos Methods for High-Dimensional Uncertainty Propagation in PDE Models*

Use generalized Polynomial Chaos (gPC) expansions to propagate input uncertainty through PDE solvers. Goals:
- Construct sparse, adaptive PC bases that mitigate the curse of dimensionality.
- Analyze convergence in high stochastic dimensions.
- Compare intrusive (Galerkin) vs. non-intrusive (collocation) implementations.

---

### 3. Robustness of Hybrid Discrete–Continuous Optimization under Stochastic Noise

**Working title:** *Robustness of Hybrid Discrete–Continuous Optimization under Stochastic Noise*

*(See also: Prof. Waisman's paper on hybrid discrete–continuous methods.)*

**Base problem:** *Hybrid Discrete–Continuous Optimization for Sparse Inverse Problems*

Many sparse inverse problems are naturally formulated with both discrete variables (e.g. support / topology selection) and continuous variables (e.g. coefficient amplitudes). A hybrid optimizer alternates between:
1. A *discrete phase* — combinatorial search or thresholding to identify the active support.
2. A *continuous phase* — gradient-based refinement of the selected coefficients.

**Central research question:**
> How robust is the discrete → continuous switching criterion when the forward model or the observations contain noise?

Specific sub-questions:
- Under what noise levels does the switching criterion still correctly identify the true support?
- Can one derive probabilistic guarantees (e.g. support recovery with high probability) analogous to compressed-sensing results?
- How should the switching threshold be adapted as a function of the noise variance?
- What is the interaction between forward-model uncertainty (stochastic PDE coefficients) and measurement noise?

This direction connects stochastic inverse problems with hybrid optimization and has direct links to ideas in Directions 1 and 2 above.