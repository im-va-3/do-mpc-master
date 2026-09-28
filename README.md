<img align="left" width="30%" hspace="2%" src="https://raw.githubusercontent.com/do-mpc/do-mpc/master/documentation/source/static/dompc_var_02_rtd_blue.png">

# Model predictive control python toolbox

[![Documentation Status](https://readthedocs.org/projects/do-mpc/badge/?version=latest)](https://www.do-mpc.com)
[![Build Status](https://github.com/do-mpc/do-mpc/actions/workflows/pythontest.yml/badge.svg?branch=develop)](https://github.com/do-mpc/do-mpc/actions/workflows/pythontest.yml)
[![PyPI version](https://badge.fury.io/py/do-mpc.svg)](https://badge.fury.io/py/do-mpc)
[![awesome](https://img.shields.io/badge/awesome-yes-brightgreen.svg?style=flat-square)](https://github.com/do-mpc/do-mpc)

**do-mpc** is a comprehensive open-source toolbox for robust **model predictive control (MPC)**
and **moving horizon estimation (MHE)**.
**do-mpc** enables the efficient formulation and solution of control and estimation problems for nonlinear systems,
including tools to deal with uncertainty and time discretization.
The modular structure of **do-mpc** contains simulation, estimation and control components
that can be easily extended and combined to fit many different applications.

In summary, **do-mpc** offers the following features:

* nonlinear and economic model predictive control
* support for differential algebraic equations (DAE)
* time discretization with orthogonal collocation on finite elements
* robust multi-stage model predictive control
* moving horizon state and parameter estimation
* modular design that can be easily extended

The **do-mpc** software is Python based and works therefore on any OS with a Python 3.x distribution. **do-mpc** was originally developed by Sergio Lucia and Alexandru Tatulea at the DYN chair of the TU Dortmund lead by Sebastian Engell. The development is continued at the [Chair of Process Automation Systems](https://pas.bci.tu-dortmund.de) (PAS) of the TU Dortmund by Felix Brabender, Joshua Adamek, Felix Fiedler and Sergio Lucia.

## Installation instructions
Installation instructions are given [here](https://www.do-mpc.com/en/latest/installation.html).

## Documentation
Please visit our extensive [documentation](https://www.do-mpc.com), kindly hosted on readthedocs.

## Citing **do-mpc**
If you use **do-mpc** for published work please cite it as:

F. Fiedler, B. Karg, L. Lüken, D. Brandner, M. Heinlein, F. Brabender and S. Lucia. do-mpc: Towards FAIR nonlinear and robust model predictive control. Control Engineering Practice, 140:105676, 2023

Please remember to properly cite other software that you might be using too if you use **do-mpc** (e.g. CasADi, IPOPT, ...)


## Step-by-step user guide

1. **Install the Python package.** Create a virtual environment, then run <code>python -m pip install do-mpc</code>. Install the optional plotting/documentation dependencies listed in the [installation guide](https://www.do-mpc.com/en/latest/installation.html) if you need them.
2. **Choose a runnable model.** From the repository root, run <code>python examples/CSTR/main.py</code> for the continuous stirred-tank reactor MPC example. The [examples](examples/) also include estimators, discrete/continuous plants, robust MPC, and LQR workflows; run one unchanged before changing its model or tuning.
3. **Define the plant.** Create a continuous or discrete model, declare state/input/parameter variables, express the right-hand side and optional algebraic equations, then call the model setup method.
4. **Configure the control loop.** Create the MPC controller, set the prediction horizon and time step, provide stage/terminal costs and input/constraint limits, and call setup. Use multi-stage robust options only after the deterministic model works.
5. **Simulate and estimate.** Connect the MPC to the simulator, initialize state and parameter values, set an initial guess, and iterate: measure the state, request the next control move, advance the simulator, and store the result.
6. **Review and refine.** Plot states, controls, and constraint activity; then tune horizon, weights, discretization, and uncertainty scenarios one at a time. Add MHE when online state or parameter estimation is required.

### Functionality map

- **Modeling and simulation:** nonlinear ODE/DAE models, algebraic equations, parameter/time-varying inputs, and orthogonal collocation discretization.
- **Control:** nonlinear/economic MPC, constraints, robust multi-stage MPC, and scenario trees.
- **Estimation:** moving-horizon state and parameter estimation (MHE).
- **Analysis:** result data, plotting/graphics, and modular components designed to be combined or extended. The complete API, solver options, and tutorials are in the [documentation](https://www.do-mpc.com/) and local [examples](examples/).

