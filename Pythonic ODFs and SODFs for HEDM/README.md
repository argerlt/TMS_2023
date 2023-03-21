# Pythonic ODFS and SODFs for HEDM
#### *Austin Gerlt*




Orientation distribution functions (ODFs) are continuous probability distributions that span non-euclidean space and describe the statistical likelihood of finding a given local orientation within a volume of interest. While complex to code from scratch, well-coded implementations such as MTEX and OIM have lead to their widespread use as an additional tool for texture analysis.

With the growing popularity of High-Resolution Electron Backscatter Diffraction (HR-EBSD) and improvments in far field High Energy Diffraction Microscopy (ff-HEDM), we now have the capability to measure spatially resolved, orientation dependent lattice strain as well. However, in the absense of good statistical descriptors, this data is often left on the table despite being collected, effectively, for free during many tests.

Past research has proposed a so-called Strain Orientation Distribution Function (SODF), but in reality, these give Strain Expectation (ie, the mean strain) as a function of orientation, and should therefore be called Strain Expectation Functions (SEF). These are still extremely useful and the best tool today for analyzing strain texture, but we have the capability to create a true SODF, wherein a probability is given for every combination of strain and orientation.

## Background

The Spherical Harmonic Orientation Distribution Function (SH-ODF)is a catch-all term for the various ODF methods based off of the format first suggested by Bunge. However, it is impossible to recreate such an ODF using his work alone, due to an error in the references as to where readers can find the generalized spherical harmonics coefficients T_l^mn(they were calculated by Viglin, not Vilenkin). These constants, in turn, were also incorrectly tabulated in the original work. This is made even more obfuscated by the fact that the term “generalized spherical harmonics” is really just referring to a subset of the Wigner D-matrices, a popular and well documented concept in quantum physics. Instead, most SH-ODF codes were written by people who personally met and interacted with Bunge, some of whom then developed proprietary commercial software from the method, making the dissemination of the correct version even more difficult. 

Fortunately, a recent publication by C.S. Man describes in excruciating detail how to produce a SH-ODF using a variety of parameterizations. In each case, the problem can be posed as a summation:

$$ω(R)=∑_{l=0}^∞∑_{m=-l}^l∑_{n=-l}^l[c_{mn}^l D_{mn}^l (R)]=P(R)$$  

Where $ω(R)$ is an ODF represented by a series summation and calculates the probably $P(R)$ of finding rotation $R$ in a random sample. $c_{mn}^l$ are the expansion coefficients, which encode the distribution information, and $D_{mn}^l (R)$ are the Wigner-D constants, which describe mutually orthogonal axes in orientation space. Modern SH-ODF codes will often perform this summation with $l≥20$, resulting in over 12,340 $c_{mn}^l$ coefficients. Each $c_{mn}^l$ constant can be calculated from a set of data by solving the related equation:

$$c_{mn}^l=(2l+1)/(V(FZ)N) ∑_{(i=i)}^Nω_actual (R_i ) D_mn^l$$

Where R_i are measurements of texture intensity, and N is the total number of measurements. Wigner D-matrices can be given in any parameterization, but as pointed out by bunge, when given in proper Euler angles, $D_{mn}^l$ can be further broken down as thus:

![CS Mann 1](https://raw.githubusercontent.com/argerlt/TMS_2023/main/resources/eqn3.png)

Where $d_{mn}^l (\theta )$ is a Wigner-d constant, which can be calculated as thus:

![CS Mann 2](https://raw.githubusercontent.com/argerlt/TMS_2023/main/resources/eqn4.png)

This calculation, while computationally expensive, is a parameter of only $\theta$, and can therefore be precalculated, thus massively speeding up this calculation

## Current Results


Empty now, but for preliminary work, check my contributions to the following  resources:


[Orix](https://github.com/pyxem/orix)

[HEXRD](https://github.com/HEXRD/hexrd)

