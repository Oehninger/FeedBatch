# Optimal Control of Recombinant Protein Production in Fed-Batch Culture

This repository contains the computational implementation of a dynamic optimization model for recombinant protein production in a fed-batch bioreactor.

The model describes the dynamics of biomass, methanol concentration, recombinant protein production, and culture volume. The feeding strategy and final cultivation time are determined through dynamic optimization using **GEKKO**.

## Model

The state variables are:

* \(x(t)\): biomass concentration
* \(s(t)\): methanol concentration
* \(r(t)\): recombinant protein concentration
* \(v(t)\): culture volume

The manipulated variable is the feed rate \(u(t)\).

Biomass growth is described using a substrate-inhibition (Haldane-type) kinetic function,

$$
\mu(s)=
\frac{\mu_{\max}s}
{K_M+s+s^2/K_I}.
$$

The optimization problem determines the feeding profile \(u(t)\) and the final cultivation time \(t_f\) to maximize recombinant protein productivity.

## Experimental comparison

Model predictions are compared with experimental data reported by **Barrigón et al. (2015)**.

The main quantities used for comparison are the increments in total biomass and total recombinant protein:

$$
\Delta XV(t)=x(t)V(t)-x(0)V(0),
$$

$$
\Delta PV(t)=r(t)V(t)-r(0)V(0).
$$

The repository includes scripts for generating the corresponding experimental/model comparison figures.

## Requirements

The implementation uses:

* Python
* NumPy
* Pandas
* Matplotlib
* GEKKO

Install the required packages with:

```bash
pip install numpy pandas matplotlib gekko
```

## Usage

Run the Jupyter notebook sequentially to:

1. define the fed-batch model;
2. solve the dynamic optimization problem;
3. construct the simulation results table;
4. compute \(\Delta XV\) and \(\Delta PV\);
5. compare model predictions with experimental data;
6. generate the figures.

## Reference

Experimental data used for model comparison were obtained from Barrigón et al. (2015) https://doi.org/10.1002/bit.25518

## Authors

Research code developed in the context of mathematical modeling and optimization of biotechnological processes.
