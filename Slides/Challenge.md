### Herschel: Informative 
Key for understanding extragalactic starformation
![](assets/Dole_2006.png?raw=true)<!-- .element height="40%" width="40%"--> ![](assets/Denis_2013.png?raw=true)<!-- .element height="40%" width="40%"-->
* $>$ 1270 deg.$^2$, accessible via [HELP](www.herschel.sussex.ac.uk) (Data release today!)
* No planned successor

Note:
As many of you will be aware, Herschel space observatory has been a transformative facility for FIR astronomy.
In particular it has been key for understanding star formation because:
* about half of starlight is absorbed by dust, radiating at infrared wavelengths
* at higher redhsifts, that peak shift towards longer wavelenghts, enabling Herschel to detect high redshift galaxies.
* For extragalactic surveys, numerous fields were observed at a mix of depths, e.g. deep COSMOS observations, to shallow but wide fields such as the GAMA fields or stripe 82. The obhjective of the HELP project has been to provide all of the Herschel extragalatic fields, alongside ancillary data products such as photometric redshifts and Spectral Energy distributions fits to the wider community and I am pleased to announce that our first data realse is being made public today, alongside the main project paper.
*  Although Ground based Facilities such as SCUBA 2 and ALMA observe in fir and submm,  do not cover the same extent of area as Herschel. There is also  no planned successor to Herschel, so in terms of having a fir observations that cover the sort of area you need to get statistical handle on rare objects which challenge galaxy formation scenarios, we are going to have to rely on Herschel for the forseeable future.


### yet confusing..
![](assets/confusion.gif)<!-- .element height="60%" width="60%"-->

Note:
That said, Herschel data is challenging to work with, mainly due to the issue of source confusion. Wiht size limitations on mirror and observing a longer wavelengths, the photometric bands have a relatively poor resolution compared to the optical.
We therefore have a challenge of working out which galaxies the fir flux is associated with, or whether the flux is coming from multiple sources


### Assigning flux to sources

|      | Blind                          | Prior driven                       |
|------|--------------------------------|------------------------------------|
| Pros | Detects all bright sources     | Distributes flux to known galaxies |
| Cons | Need to assign flux to sources | Miss unknown sources               |

Data Products are part of Data Model

Note:
Normal source extraction won't work
Don't know what or how much source contributes to FIR blob
Solution is to do list driven approach
use prior information to build data model, infer model on maps
Wrong model = wrong results = wrong interpretation


Interesting objects from blind catalogues,

* **High redshift starbursts**: e.g. Riechers et al. 2013
* **Lenses**: e.g. Wardlow et al. 2013, Negrello et al. 2017
* **extreme starbursts**: e.g. Rowan Robinson et al. 2018

<div class="r-stack">
  <img class="fragment fade-out" data-fragment-index="0" src="./assets/hfls3_SPIRE_small.jpeg" width="40%" height="80%">
  <img class="fragment current-visible" data-fragment-index="0" src="./assets/SDP81_ALMA_HST.jpeg" width="40%" height="80%">
  <img class="fragment" src="assets/MRR_2018_fig3R.png" width="40%" height="80%">
</div>

Note:
The blind source detection approach has been very fruitful. For example, they have been used to detect high redshift starbursts such as HFLS3,
 many of the bright objects have been confimred to be lensed galaxies through follow up observations.
 There are also some of the blind source objects thought to be galaxies undergoing extreme starformation, on the order of 20000 -30000 solar mases per year.
 Given the limitations of the blind source approach, do we get the same interpreatiton when we take a prior based appraoch to modelling the Hershcel maps and can machine learning help.
