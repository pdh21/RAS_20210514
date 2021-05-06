## Scientific Simulators
We can write complex simulations to describe phenomena of interest

* Dark matter sims (e.g. Millenium, Illustris, Bluetides etc)
* Other disciplines (e.g. particle physics, climate models, etc)

What if we could run them in reverse?

Note: Many domains of science have developed complex simulations to
describe phenomena of interest. While these simulations provide
high-fidelity models, they run one way, from parameters to synthetic data

## Probabilistic Programming
integrating inference and simulation
1) the ability to draw values at random from distributions 
2) the ability to condition values of variables in a program via observations.
> Define probability models & solve automatically

![](Slides/assets/probprog.png?raw=true)<!-- .element height="50%" width="50%" -->


## What has made probabilisiitc programming feasible?
e.g. HMC, autodiff, hardware,variational inference
software:
* Stan
* Pymc
* Numpyro


## Why would you want to use probabilisitic programming..
* want to run simulations in reverse
* allows complex models and model close to raw data without using statistical summaries e.g. Lum functions, stacking etc
