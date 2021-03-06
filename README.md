Research Goal:
1) Determine if there is hemisphere-dependent change in cortical and subcortical white matter (measured by d-MRI features) in patients who recover motor function through brain-computer interface (BCI) therapy.

Programs: 
1) SRC_Conversion.m: MATLAB script that converts raw DICOM (scanner output) image into SRC file for diffusion tensor reconstruction. 
2) GQIReconstruction.m: MATLAB function that reconstructs the diffusion tensors of an SRC file using GQI (generalized q-sampling imaging), a model-free technique to estimate the water diffusion within white matter. Model-free methods like GQI do not make assumptions of the underlying water distrubtion (DTI assumes a Gaussian for comparison) which do not limit the empirical data reconstruction with any assumptions. 
3) dtiFunctions.py: Python program that contains multiple classes and methods required for analyzing the DTI measures post-reconstruction. These methods are called in hemisphereAnalysis.py and cerebellumAnalysis.py (not yet uploaded). 
    
    a) data_initialization is a class containing three methods required to be run in series in order to properly load data. load_pt_data() is the first method that must be called in hemisphereAnalysis.py and cerebellumAnalysis.py in order to load UEFM scores as data frames and extract the list of patient IDs from them. load_hemispheric_data() or load_cerebellar_data() is the second method which must be called depending on the analysis seeking to be run. load_hemispheric_data() returns the pre- and post-therapy DTI measures (fractional anisotrophy and mean diffusivity) depending on which the user seeks to study. load_cerebellar_data() does the same for pre-and post-therapy DTI measures but from the cerebellar hemsipheres only. It also retuns the pre-aand post-therapy FA and MD sampled from ROI- and tract-based techniques. For the smaller ROIs defined in the cerebellum (compared to the cerebral cortex), two sampling techniques are required to ensure robustness of the collected data. 
    
Unsupported Programs: 
1) Fig2.py, Fig4.py, SFig1.py, and SFig2.py are older scripts which do no not reflect the updated patient data and motor scores. They should only be run for quick visualization of the original data while understanding that it does not represent the most up-to-data results. 
