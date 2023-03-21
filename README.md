# TMS 2023 -Supplementary information

Hello, and thanks for taking an interest in my work!

Below are copies of the abstracts for both my talk and my poster, and copies of both can be found in the attached folders. Please feel free to email me any related followup questions

### **Poster L-4: Pythonic ODFs and SODFs for EBSD and Far Field HEDM**

Orientation distribution functions (ODFs) are continuous probability distributions that span non-euclidean space and describe the statistical likelihood of finding a given local orientation within a volume of interest. While complex to code from scratch, well-coded implementations such as MTEX and OIM have lead to their widespread use as an additional tool for texture analysis.

With the growing popularity of High-Resolution Electron Backscatter Diffraction (HR-EBSD) and improvments in far field High Energy Diffraction Microscopy (ff-HEDM), we now have the capability to measure spatially resolved, orientation dependent lattice strain as well. However, in the absense of good statistical descriptors, this data is often left on the table despite being collected, effectively, for free during many tests.

Past research has proposed a so-called Strain Orientation Distribution Function (SODF), but in reality, these give Strain Expectation (ie, the mean strain) as a function of orientation, and should therefore be called Strain Expectation Functions (SEF). These are still extremely useful and the best tool today for analyzing strain texture, but we have the capability to create a true SODF, wherein a probability is given for every combination of strain and orientation.

### **Applications of Min-cut Algorithms for Image Segmentation and Microstructure Reconstruction**

Graph cut algorithms are a useful set of techniques for separating out or clustering connected data. In particular, the Boykov Min-cut/Max-flow algorithm is adopted to efficiently run on uniform 2d or 3d grids of data, such as would be seen in an image or 3d raster dataset. These techniques see significant usage in both the medical imaging community (for example, identifying tumors in MRIs) and in ML image processing (for example, object detection). 
This talk will show several cases in Material Science fields wherein this algorithm can be used to efficiently segment datasets that other algorithms such as watershed, edge detection, or basic thresholding might fail. Notably, this is used for automated spot detection in far field HEDM, and prior Austenite parent reconstruction on Martensitic EBSD scans.


