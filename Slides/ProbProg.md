## Probabilistic Programming
Traditioanl use of simulators e.g. Many domains of science have developed complex simulations to
describe phenomena of interest. While these simulations provide
high-fidelity models, they are poorly suited for inference and lead
to challenging inverse problems

integrating inference and simulation
1) the ability to draw values at random from distributions 
2) the ability to condition values of variables in a program via observations.

## What has made probabilisiitc programming feasible?
e.g. HMC, autodiff, hardware,variational inference
software:
* Stan
* Pymc
* Numpyro



## Why would you want to use probabilisitic programming..
* want to run simulations in reverse
* allows complex models and model close to raw data without using statistical summaries e.g. Lum functions, stacking etc
