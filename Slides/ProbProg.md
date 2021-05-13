### How can Machine Learning Help?

|      | Discriminative                         | Generative                     |
|------|--------------------------------|------------------------------------|
| Pros | <sub><sub>Big data, v. good for predictions, can capture intricate structure</sub> </sub>| <sub><sub>principled estimate of uncertainty, requires stronger modelling assumptions, easier to interpret</sub></sub> |
| Cons | <sub><sub>difficult to impart domain knowledge, difficult to interpret, lack principled estimate of uncertainty</sub></sub>| <sub><sub>requires stronger modelling assumptions, challenging to fit, often intractable with large data</sub></sub> |

Note:
One way to split up machine learning approaches is via those that are discriminative
**Discriminative** e.g. Neural_net, svm, focus on directly learning a predictive model: given training data
they learn a parametrised mapping from the inputs to the outputs that can be used directly to make predictions for new inputs 
if our objective is prediction, then it is simplest to solve that problem directly, rather than try and solve some more general proble
**Generative** e.g. Naive bayes, probabilistic models, models how data is generated, 


### Generative models $\approx$ invertable simulators
We can write complex simulations
* Dark Matter sim: e.g. Millenium, Illustris, Bluetides
* Radiative Transfer models

![](assets/probprog.png?raw=true)<!-- .element height="40%" width="40%" -->

Note:
Many domains of science have developed complex simulations to
describe phenomena of interest. While these simulations provide
high-fidelity models, they run one way, from parameters to synthetic data
**Probabilistic Programming** Define probability models & solve automatically
Up to fairly recently, inference has been challenging, required writing the inference algorithms for each problem. Prob prog is changing that, abstracts out the complexity of inference algorithms, allowing us to focus oin builing models for science


### What has made probabilistic programming feasible?
**Algorithms**: MCMC, NUTS HMC, Variational Inference, auto-differentiation

**Software**:

![](https://mc-stan.org/docs/2_18/reference-manual/img/logo_tm.png)<!-- .element height="20%" width="20%" --> ![](https://cdn.rawgit.com/pymc-devs/pymc3/master/docs/logos/svg/PyMC3_banner.svg)<!-- .element height="20%" width="20%" --> ![](https://github.com/pyro-ppl/numpyro/blob/master/docs/source/_static/img/pyro_logo_small.png?raw=true)<!-- .element height="20%" width="20%" -->

Note:
* recent developments in algorithms such as no u turn hamiltonian monte carlo and variational inference, bioth of which use auto-differentiation.
* These inference algorithms have been packaged into userfriendly software such as Stan, PyMC3 and Pyro or Numpyro


### Why is this the approach for me?
We have domain expertise: e.g. 
* catalogues and photoz from other wavelengths
* Spectral Energy Distributions (SEDs), 
* some idea of statistical relations e.g. SFR vs redshift, Luminosity Function etc

Usual approach of producing catalogues, fitting SEDs, is very lossy for Herschel data.

Note:
So why is using probabilisitic programming to build models appropriate for me, well. I have domain knowledge. We are taking a prior based approach
e.g. we have a list of galaxies we think teh flux is coming from, photometric redshifts give us some idad of there redshift, 
we have a good understanding of the spectral energy distribution of galaxies, and some idea of the population statistics 
The issue of source confusion results in degeneracies which make the usual approach of first constructing catalogues, then doing SED fitting, followed by fitting statistical models a lossy one. Better to try and do all of that simultanously.  