# Pythonic ODFS and SODFs for HEDM
### *by some people*

This one needs actual stuff. try some links real quick


## Background

The Spherical Harmonic Orientation Distribution Function (SH-ODF)is a catch-all term for the various ODF methods based off of the format first suggested by Bunge. However, it is impossible to recreate such an ODF using his work alone, due to an error in the references as to where readers can find the generalized spherical harmonics coefficients T_l^mn(they were calculated by Viglin, not Vilenkin). These constants, in turn, were also incorrectly tabulated in the original work. This is made even more obfuscated by the fact that the term “generalized spherical harmonics” is really just referring to a subset of the Wigner D-matrices, a popular and well documented concept in quantum physics. Instead, most SH-ODF codes were written by people who personally met and interacted with Bunge, some of whom then developed proprietary commercial software from the method, making the dissemination of the correct version even more difficult. 

Fortunately, a recent publication by C.S. Man describes in excruciating detail how to produce a SH-ODF using a variety of parameterizations. In each case, the problem can be posed as a summation:

$$ω(R)=∑_{l=0}^∞∑_{m=-l}^l∑_{n=-l}^l[c_{mn}^l D_{mn}^l (R)]=P(R)$$  

Where $ω(R)$ is an ODF represented by a series summation and calculates the probably $P(R)$ of finding rotation $R$ in a random sample. $c_{mn}^l$ are the expansion coefficients, which encode the distribution information, and $D_{mn}^l (R)$ are the Wigner-D constants, which describe mutually orthogonal axes in orientation space. Modern SH-ODF codes will often perform this summation with $l≥20$, resulting in over 12,340 $c_{mn}^l$ coefficients. Each $c_{mn}^l$ constant can be calculated from a set of data by solving the related equation:

$$c_{mn}^l=(2l+1)/(V(FZ)N) ∑_{(i=i)}^Nω_actual (R_i ) D_mn^l$$

Where R_i are measurements of texture intensity, and N is the total number of measurements. Wigner D-matrices can be given in any parameterization, but as pointed out by bunge, when given in proper Euler angles, $D_{mn}^l$ can be further broken down as thus:

![CS Mann 1](https://raw.githubusercontent.com/mesoOSU/Mart2Aust_Hackathon/master/doc/_static/img/hackathon_logo.png)

Where $d_{mn}^l (\theta )$ is a Wigner-d constant, which can be calculated as thus:

![CS Mann 2](https://raw.githubusercontent.com/mesoOSU/Mart2Aust_Hackathon/master/doc/_static/img/hackathon_logo.png)

This calculation, while computationally expensive, is a parameter of only $\theta$, and can therefore be precalculated, thus massively speeding up this calculation

## Current Results


Empty now, but for preliminary work, check my contributions to the following  resources:


[Orix](https://github.com/pyxem/orix)

[HEXRD](https://github.com/HEXRD/hexrd)

