# anitemp
Template files to process structural magnetic resonance images from primates in [CAT12](http://dbm.neuro.uni-jena.de/cat/)/[SPM12](https://www.fil.ion.ucl.ac.uk/spm/). The templates include T1 and T2 registration templates, a tissue probability map (TPM) for segmentation, a brain mask, and a Dartel registration template (Template 1-6).  The templates based on the Rilling's dataset (Rilling & Insel, 1999) and was created by Robert Dahnke for structural preprocessing in CAT12/SPM12.  Because of the limited number of subjects multiple species were averaged.  The greater apes template consist of 12 images from chimpanzee, bonobos, orang-utan, and gorillas.  For further description see (Franke et al., 2017).  

If you use any of the templates please site website and the Rilling and Franke paper. 


## Primate preprocessing in CAT12
To use the templates in CAT12 you have to copy the files into a _templates_animals_ sub directory in the cat toolbox directory and start CAT with ```
cat12('oldworldmonkey')``` or ```cat12('greaterapes')``` that will open CAT12 in the developer mode with many further preprocessing options. By default CAT12 now uses Shooting you have to switch from Shooting to Dartel registration by setting the _Method_ field in the _Spatial Registion Option_ to 0.  The most critical step is the affine registration and the image should be roughly alligned to the template. You can use the SPM Display function do check and reorientate the images. 
Surface-based preprocessing is and registration to the human FreeSurfer average brain is possible in principle and support interspecies coparison ([example]()) because the major gyri and sulci are quite similare.

Moreover, a chimplanzee template can be found [here](https://github.com/viko18/JunaChimp) that also include batch scripts to analyse aging in the 10 example chimps from [chimpanzeebrain.org](http://www.chimpanzeebrain.org/) or typing ```cat12('chimps')``` in the matlab command line to start CAT12 with chimpanzee settings. 

However, due to the ongoing developement of the human preprocessing pipeline and the quite low priority of the primate processing as my hobby, the processing of primates is suffering from from time to time, due to some hard coded functions (e.g. morphometric operations with fixed voxel size).  Besides preprocessing erros and bugs also the image quality is often a problem and a good contrast between gray and white matter is required.  In many 1.5 Tesla images the myelinated regions (motorcortex/occiptial) are often not clear differentiable even for experient experts and are often missclassified as white matter, resulting in a strong underestimation of the local thickness. 


## References: 
* Rilling, JK, Insel, TR. The primate neocortex in comparative perspective using magnetic resonance imaging. Journal of Human Evolution, 37, 191-223. 1999.
* Franke, K, Clarke, GD, Dahnke, R, Gaser, C, Kuo, AH, Schwab, M, Nathanielsz P. Premature Brain Aging in Baboons Resulting from Moderate Fetal Undernutrition. Frontiers in Aging Neuroscience. 2017
* Vikery, S, ... 
