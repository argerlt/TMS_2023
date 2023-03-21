# Applications of min-cut algorithms for image segmentation and microstructure reconstruction

#### *Austin Gerlt, Alexander Brust, Eric Patyon, Steve Niezgoda*



**Abstract**
Graph cut algorithms are a useful set of techniques for separating out or clustering connected data. In particular, the Boykov Min-cut/Max-flow algorithm is adopted to efficiently run on uniform 2d or 3d grids of data, such as would be seen in an image or 3d raster dataset. These techniques see significant usage in both the medical imaging community (for example, identifying tumors in MRIs) and in ML image processing (for example, object detection). 
This talk will show several cases in Material Science fields wherein this algorithm can be used to efficiently segment datasets that other algorithms such as watershed, edge detection, or basic thresholding might fail. Notably, this is used for automated spot detection in far field HEDM, and prior Austenite parent reconstruction on Martensitic EBSD scans.


Related publication links:

[Probabilistic Reconstruction of Austenite Microstructure from Electron Backscatter Diffraction Observations of Martensite](https://doi.org/10.1017/S1431927621012484)

[Application of the Maximum Flow–Minimum Cut Algorithm to Segmentation and Clustering of Materials Datasets](https://doi.org/10.1017/S1431927619014569)
