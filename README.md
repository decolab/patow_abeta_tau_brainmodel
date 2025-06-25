# Whole-brain Modeling of Amyloid-Beta and Tau in Alzheimer’s Disease

**Python implementation for modeling the differential effects of Amyloid-Beta and Tau accumulation in Alzheimer’s disease (AD)**

This repository contains the source code used in the study:

> Patow, G., Stefanovski, L., Ritter, P., Deco, G., Kobeleva, X., & for the Alzheimer’s Disease Neuroimaging Initiative. (2023).  
> *Whole-brain modeling of the differential influences of Amyloid-Beta and Tau in Alzheimer’s Disease*.  
> Accepted at *Alzheimer’s Research & Therapy*.

The study uses whole-brain computational modeling to investigate the distinct contributions of Amyloid-Beta (Aβ) and Tau pathology to altered brain dynamics in Alzheimer's disease. Simulations integrate empirical fMRI and diffusion MRI data, and use a Hopf oscillator framework to assess the network-level impact of protein accumulation.

---

## Purpose & Scope

- Simulate large-scale brain activity using subject-specific structural connectomes and burden maps of Aβ and Tau.
- Quantify alterations in oscillatory dynamics and compare across clinical stages (Healthy Controls, MCI, AD).
- Evaluate model performance with empirical data using parameter tuning and statistical analysis.
- Investigate AT(N) biomarker classification as a stratification strategy.

---

## Repository Structure

- `setup.py`: Main configuration file for dataset paths and parameters.
- `dataLoader.py`: Script to load multimodal imaging data.
- `Prepro.py`: Preprocessing script to compute model parameters (e.g., global coupling G).
- `plotPrepro.py`: Visualizes preprocessing outputs.
- `pipeline2.py`: Main modeling pipeline using Hopf-based whole-brain dynamics.
- `plot3DBrainBurdens.py`: Generates 3D plots comparing Aβ and Tau for diagnostic groups.
- `Shuffling.py`: Generates comparisons with randomly shuffled data.
- `plotParmComparisonAcrossCohort.py`: Produces figures stratified by diagnosis or AT(N) category.
- `classific_AT(N).py`: Performs biomarker-based classification.
- `setup_ATN.py`: Alternate configuration file for AT(N)-based grouping.

---

## Requirements

- Python 3.x
- Numpy, Matplotlib, Nibabel, and other scientific libraries
- Empirical imaging data from the Alzheimer’s Disease Neuroimaging Initiative (ADNI)
- Preprocessed structural connectomes and burden maps

---

## Usage Instructions

1. setup.py is the main configuration file. It should be modified first. This file uses dataLoader.py to perform the actual loading of the files.
2. Prepro.py should be executed next, as it computes the preprocessing of the model (computation of G, we in the code) and uses the previous one.
3. plotPrepro.py plots the results of Prepro.py. Should be done AFTER Prepro.py.
4. Finally, pipeline2.py should be executed. This file was written before the big re-factorization of the WholeBrain library, so it partially uses its newer features. Also, it uses the G=3.1 value found at Prepro.py.
5. plot3DBrainBurdens is used to plot the nice 3D plots comparing ABeta and Tau for HC, MCI and AD.
6. Shuffling.py is used for the comparisons with shuffled random data.
7. plotParmComparisonAcrossCohort.py is used for plotting the different figures in the paper, see comments within at the respective boolean variables.

If the AT(N) classification should be used, first run classific_AT(N).py, and then configure and use setup_ATN.py. All the rest of the system should continue working as before (this only affects the final cohort grouping for plotting).

---

## Data Sources & Ethics

- This project uses anonymized data from the Alzheimer’s Disease Neuroimaging Initiative (ADNI).
- All use of data complies with ADNI terms of access and institutional ethical guidelines.

---

## Citation

If you use this code, please cite:

Patow, G., Stefanovski, L., Ritter, P., Deco, G., Kobeleva, X., & for the Alzheimer’s Disease Neuroimaging Initiative. (2023).  
*Whole-brain modeling of the differential influences of Amyloid-Beta and Tau in Alzheimer’s Disease*.  
*Alzheimer’s Research & Therapy*. Accepted for publication.

---

## License

This project is released under the MIT License.  
© 2023 Gustavo Patow

---

## Contact

For questions or support, please contact:  
**Gustavo Patow**  
📧 [gustavo.patow@upf.edu](mailto:gustavo.patow@upf.edu)  
CNS Department, University Pompeu Fabra
