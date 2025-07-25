# UDE‑Damped‑Spring

Modeling a damped spring–mass system with an unknown damping term using Universal Differential Equations (UDEs) in Julia. The project embeds a neural network into the ODE to learn latent damping dynamics from partial, noisy data and forecast displacement and velocity trajectories.

---

## Overview

This repository demonstrates a hybrid physics–ML approach in Julia for a damped spring–mass system where the damping coefficient is unknown. By embedding a small neural network inside the differential equation solver, the model learns the missing damping behavior directly from noisy displacement and velocity measurements. Training on only 30% of the data over a 10 s window, the UDE accurately forecasts the full system response, illustrating how known physics and data-driven components can be combined in Scientific Machine Learning.

---

## Features

- **Physics‑informed hybrid modeling**: Known spring–mass dynamics combined with a learned damping term.  
- **Data efficiency**: Training uses only 30% of synthetic noisy data (0–10 s, Δt = 0.1 s).  
- **Forecasting**: Predicts both displacement and velocity over the full interval.  
- **Visualization**:  
  - Noisy training data plots  
  - Predicted vs. noisy trajectories  
  - Loss vs. iteration curve  
  - Training performance diagnostics  
- **Modular codebase**: Easily swap neural‑network architectures or physical parameters.  

---

## Requirements

- Julia ≥ 1.8  
- Jupyter or Pluto with a Julia kernel  
- Packages:  
  ```julia
  using DifferentialEquations
  using Optimization, OptimizationOptimisers, OptimizationZygoteExt
  using Lux           # Neural network definitions
  using Random, Plots
