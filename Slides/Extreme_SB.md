### XID+SED: Probabilistic De-blender with SED emulator

![](assets/pgm_annotated.png)<!-- .element height="80%" width="80%"-->

Note:
Using this probabilisitc appraoch, we developed XID+ as part of HELP to use prior information on sources to extract FIR fluxes. 
For the HELP DR1, we used positional information, as illustrated by the black variables in our probabilisitic graphical model. Taking this further, we can now incoprorate SED modelling via an emulator and use HELP photometric redshifts as additioanl prior information. We can also impart more domain knowledge, that to first order,
SFR linearly increases with redshift, with some dispersion. With the global parameters m, c and sigma_sfr governing the strength of that relation.


### Emulating Cigale ![](https://gitlab.lam.fr/uploads/-/system/project/avatar/11/logo_cigale.png)<!-- .element height="8%" width="8%"-->
Emulating complex models is not new (e.g. Silva et al. 2011, Alsing et al. 2020)

Using them inside a prob. model is!

![](assets/emulator_net.png)<!-- .element height="40%" width="40%"-->

Note:
Incoporating SED models is not straightforward. THey are complex models. However, we can emulate our favourite SED code using neural networks. This is not a new idea, having been used to emualte the GRASIl radiatiabve trasnfer code and SPS models. What is novel, is using them inside a probabilisitic model.
Not only does Neural net speed up SED fitting, it makes it differentiable, allowing us to use HMC and SGD in inference. Build MIMO NeuralNet model Using JAX, an Autograd and XLA python library. Used by Numpyro


### Fitting Extreme SB Candidates
![](assets/original_map.png)<!-- .element height="80%" width="80%"-->

Two Models:

1) All sources with >=3 detections in Opt./NIR 

2) Same, but with **only one** source within 18'' of candidate

Note:
We are using this XID+SED to explore the extreme starburst candidates, identified from the blind catalogue. And to show you how this works, lets look at an example. We do this by constructing two models.
The first contains all the sources from the HELP masterlist with detections in 3 or more opt/nir bands, including the candidate.
Our alternative model uses the same, but to mimic the assumption of the blind catalogue we remove all sources that are within 18'' of the candidate.


### Comparing the models
Bayesian P value maps (think robust residual map)

<span style="color:Blue "> too much flux in model  </span>, <span style="color:Red "> not enough flux in model  </span>

![](assets/Bpval.png)<!-- .element height="60%" width="60%"-->
![](assets/Bpval_alt.png)<!-- .element height="60%" width="60%"-->

Note:
Because we are using a Bayesian inference approach to fitting hte maps, we dont get one most likely answer, we get a range of possible fits, that are deemed probable. WE can make use of all the probable fits to construct a more robust residual map, which we call Bayesian P value maps. They provide a visual check for where a model is appropriate. 
Where the model has too much flux comapred tot he data, and red for where the model create enough flux seen in the data
As you can see, our first model provides an almost perfect fit to the data,where as the alternate model, which is mimicing the approximation of hte blind catalogue, i.e. that all the flux belongs to one galaxy, has a poor fit. 
By using the blind catalogues on their own, without considering whether it is an appropriate data model, can lead to misinterpreatitons and is why we want to model as much of our data pipeline as possible simultansoly.


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
Remember we imparted a linear relationship between SFR and redshift, but gave the model the freedom to find m, c and dispersion.
Our model also provides us the information on these hierarchical parameters. Again , red is prior values, and blue is inferred. On the right hand side, we can see what that relation looks like, and ohwo our individual galaxies fit on top.
Fitting on samll regions is interesting, but the real gain will be extending to fit larger regions, and moving beyond the linear relationship to more principled parameterisations such as the Schecter functions.


### Conclusions

* <span style="color:DarkBlue "> Probabilistic Programming enables us to build and **infer** more complex probabilistic models </span>
* <span style="color:DarkRed "> Probabilistic models enables us to combine data with our own expertise </span>
* <span style="color:DarkBlue "> Traditional data products are a lossy data compression for Herschel </span>
* <span style="color:DarkRed "> An alternative interpretation for many of the Extreme Starburst candidates </span>

![](assets/Help_Logo.png?raw=true)<!-- .element height="15%" width="15%" --> [http://herschel.sussex.ac.uk/](http://herschel.sussex.ac.uk/)

