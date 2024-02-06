# GLM Analysis of Parkinson's Disease and Healthy Controls Using OpenNeuro DS001907

## Overview
This project aims to explore the brain activity differences between Parkinson's disease patients and healthy controls using the ds001907 dataset from OpenNeuro. By employing General Linear Model (GLM) analysis, we sought to uncover patterns that might contribute to our understanding of Parkinson's disease.

## Preprocessing Steps
Each subject's data underwent several preprocessing steps to ensure quality and consistency across analyses:
- **High-Pass Filtering:** Applied using nilearn, with a sigma value set to 16.5 volumes.
- **Despiking:** Performed using AFNI's `3dDespike`.
- **Slice Timing Correction:** Executed with AFNI's `tshift`.
- **Spatial Smoothing:** Utilized AFNI's 4mm FWHM filter for blurring.

## Analysis Workflow
1. **First-Level GLM Analysis:** Individual analysis to model task-related brain activity.
2. **Second-Level GLM Analysis:** Comparison between healthy individuals and Parkinson's disease patients, highlighting substantial inter-individual variability.
3. **Enhanced Second-Level GLM Analysis:** 50 random iterations of the second-level analysis for each group to mitigate individual differences, focusing on disease-specific changes.
4. **Validation:** Repeating the enhanced analysis to confirm the minimization of individual differences, with p-values indicating successful homogenization.

## Results and Discussion
Initial analyses identified statistically significant differences (p<0.05) in regions such as the basal ganglia, cerebellum, frontal lobes, and thalamus. However, after applying multiple comparison corrections (FPR, FDR, FWER), no significant differences were detected. This underscores the importance of robust statistical methods in neuroimaging studies and highlights the challenges in detecting subtle brain activity changes amidst stringent correction criteria.

## Conclusion
Our findings highlight the complexities of neuroimaging analysis in distinguishing between disease-specific changes and individual variability. While initial results suggested significant differences, the application of multiple comparison corrections provided a cautionary tale on the interpretability of such findings. Future research should consider larger sample sizes or more sensitive analysis methods to navigate the balance between sensitivity and specificity in neuroimaging studies.

## Tools Used
- **AFNI:** For despiking, slice timing correction, and spatial smoothing.
- **nilearn:** For high-pass filtering.
