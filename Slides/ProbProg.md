### How can Machine Learning Help?

|      | Discriminative                         | Generative                     |
|------|--------------------------------|------------------------------------|
| Models | <sub><sub>Neural Networks, SVM, Decision trees</sub></sub> | <sub><sub>Probabilistic models</sub></sub>|
| Pros | <sub><sub>Works with big data, v. good for predictions, can capture intricate structure</sub> </sub>| <sub><sub>principled estimate of uncertainty, requires stronger modelling assumptions, easier to interpret</sub></sub> |
| Cons | <sub><sub>difficult to impart domain knowledge, difficult to interpret, lack principled estimate of uncertainty</sub></sub>| <sub><sub>requires stronger modelling assumptions, challenging to fit, often intractable with large data</sub></sub> |

Note:
**Discriminative** focus on directly learning a predictive model: given training data
they learn a parametrised mapping from the inputs to the outputs that can be used directly to make predictions for new inputs 
if our objective is prediction, then it is simplest to solve that problem directly, rather than try and solve some more general proble
**Generative** models how data is generated, 


#### Generative models $\approx$ invertable simulators
We can write complex simulations
* Dark Matter sim: e.g. Millenium, Illustris, Bluetides
* Radiative Transfer models

![](assets/probprog.png?raw=true)<!-- .element height="40%" width="40%" -->

Note:
Many domains of science have developed complex simulations to
describe phenomena of interest. While these simulations provide
high-fidelity models, they run one way, from parameters to synthetic data
**Probabilistic Programming** Define probability models & solve automatically


#### What has made probabilistic programming feasible?
**Algorithms**: MCMC, NUTS HMC, Variational Inference, auto-differentiation

**Software**:

![](https://mc-stan.org/docs/2_18/reference-manual/img/logo_tm.png)<!-- .element height="20%" width="20%" --> ![](https://cdn.rawgit.com/pymc-devs/pymc3/master/docs/logos/svg/PyMC3_banner.svg)<!-- .element height="20%" width="20%" --> ![](https://github.com/pyro-ppl/numpyro/blob/master/docs/source/_static/img/pyro_logo_small.png?raw=true)<!-- .element height="20%" width="20%" -->


#### Why is this the approach for my challenge?
We have domain expertise: e.g. 
* SEDs, 
* catalogues and photoz from other wavelengths
* some idea of statistical relations e.g. Luminosity functions

Usual approach of producing catalogues, fitting SEDs, learning LF etc very lossy for Herschel data.
