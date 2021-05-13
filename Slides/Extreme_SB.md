### XID+SED: Probabilistic De-blender with SED emulator

![](assets/pgm_annotated.png)<!-- .element height="60%" width="60%"-->

Note:
Using this probabbilisitc appraoch, we developed XID+ as part of HELP to use prior information on sources to extract FIR fluxes. 
For the HELP DR1, we have only used positional information, as illustrated by the black variables in our graphical model. Taking this further, we can now incoprorate SED modelling and photometric redshifts as additioanl prior information. We can also impart more domain knowledge, that to first order,
SFR linearly increases with redshift, with some dispersion. With the global parameters m, c and sigma_sfr governing the strength of that relation.


### Emulating Cigale ![](https://gitlab.lam.fr/uploads/-/system/project/avatar/11/logo_cigale.png)<!-- .element height="8%" width="8%"-->
Emulating complex models is not new (e.g. Silva et al. 2011, Alsing et al. 2020)

Using them inside a prob. model is!

![](assets/emulator_net.png)<!-- .element height="40%" width="40%"-->

Note:
To incorporate SED models, we can emulate our favourite SED code using neural networks. This is not a new idea, having beenn used to emualte the GRASIl radiatiabve trasnfer code and SPS models. What is novel, is using them inside a probabilisitic model.
Not only does Neural net speed up SED fitting, it makes it differentiable, allowing us to use HMC and SGD in inference. Build MIMO NeuralNet model Using JAX, an Autograd and XLA python library. Used by Numpyro


### Fitting Extreme SB Candidates
![](assets/original_map.png)<!-- .element height="80%" width="80%"-->

Two Models:

1) All sources with >=3 detections in Opt./NIR 

2) Same, but with **only one** source within 18'' of candidate

Note:
We are using this XID+SED to explore the extreme starburst candidates, identified from the blind catalogue. And to show you how this works, lets look at an example. We construct two models.
The first contains all the sources from the HELP masterlist with detections in 3 or more opt/nir bands, including the candidate.
Our alternative model uses the same, but to mimic the assumption of the blind catalogue we remove all sources that are within 18'' of the candidate.


### Comparing the models
Bayesian P value maps (think robust residual map)
<span style="color:Blue "> too much flux in model  </span>, <span style="color:Red "> not enough flux in model  </span>

![](assets/Bpval.png)<!-- .element height="65%" width="65%"-->
![](assets/Bpval_alt.png)<!-- .element height="65%" width="65%"-->

Note:
The Bayesian P value maps are a better visualisation for checking which model is most appropriate and are constructed by comparing all the posterior sampels, seen in hte previous animations, with the original data. You can think of htem as moer robust resifual maps, with blue pixels showing where the model has too much flux comapred tot he data, and red for where the model create enough flux seen in the data
As you can see, our first model provides an almost perfect fit to the data,where as the alternate model has a poor fit. 


### The Inferred Parameters
![](assets/joint_phys_params.png)<!-- .element height="55%" width="55%"-->

Note:
Taking our preferred model forward, we can now look at the inferred physical parameters. Our joint plot shows the prior in red, i.e. all the possible values out model would allow before inferring on the data, and our posterior in blue. We can see that the redshift and SFR are considerbaly less than the what you would get if you were to use the blind catalogues


### Inferred hierarchical relation 

![](assets/hier_z_sfr.png)<!-- .element height="35%" width="35%"--> ![](assets/z_sfr_relation.png)<!-- .element height="35%" width="35%"--> 

Currently fitting area around interesting sources,

**Next Step**: Fit to larger regions to constrain hierarchical relations

Note:
That example has demonstrated a useful outcome of this appraoch for investigating particualr objects in more detail. Another outcome is the inferred hoerarchica lrelation.
Remember we imparted a linear relationship between SFR and redshift, but gavethe model the freedom to find m, c and dispersion.
Our model also provides us the information on these hierarchical parameters. Again , red is prior values, and blue is inferred. On the right hand side, we can see what that relation looks like, and ohwo our individual galaxies fit on top.
Fitting on samll regions is interesting, but the real gain will be extending to fit larger regions, and moving beyond the linear relationship to more principled parameterisations such as the Schecter functions.


### Conclusions

* <span style="color:DarkBlue "> Probabilistic Programming enables us to build and **infer** more complex probabilistic models </span>
* <span style="color:DarkRed "> Probabilistic models enables us to combine data with our own expertise </span>
* <span style="color:DarkBlue "> Traditional data products are a lossy data compression for Herschel </span>
* <span style="color:DarkRed "> An alternative interpretation for many of the Extreme Starburst candidates </span>

![](assets/Help_Logo.png?raw=true)<!-- .element height="15%" width="15%" --> [http://herschel.sussex.ac.uk/](http://herschel.sussex.ac.uk/)

