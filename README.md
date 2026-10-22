# metabolic-image-analysis
A python data pipeline for extracting, segmenting, and visualizing raw confocal microscopy autofluorescence data to quantify cellular metabolic states.

## Overview
This project processes raw confocal microscopy images (CZI format) to quantify dynamic changes in cellular metabolism. The dataset is derived from university biophysical research focused on monitoring cell metabolism with NAD(P)H fluorescence lifetime imaging and utilizing redox cofactors as intrinsic probes of metabolic state. By building an automated Python pipeline, I extracted, transformed, and visualized this autofluorescence data to compare NADH levels in cells treated with Glucose (25mM) vs. Galactose (10mM).

## Technical Stack
* **Languages:** Python
* **Libraries:** `numpy`, `matplotlib`, `tifffile`, `czifile`
* **Techniques:** Image Segmentation (Boolean Masking), ETL (Extract, Transform, Load), Time-Series Analysis, Data Visualization.

## Methodology & Pipeline
1. **Data Extraction & Conversion:** Automated the batch conversion of proprietary `.czi` confocal microscopy files into workable `.tiff` image arrays.
2. **Image Processing & Segmentation:** Applied boolean segmentation masks (pixel brightness threshold > 256) to isolate cellular regions from background noise across image slices.
3. **Data Transformation:** Calculated mean fluorescence intensity across 15 timepoints (30-second intervals) and normalized the output to baseline NADH percentages using FCCP and Rotenone reference baselines.

## Key Visualizations

### 1. Fluorescence Intensities Over Time
*Tracks multivariable cellular response across a 450-second timeline.*
![Time Series Graph](<img width="569" height="443" alt="Flourescence intensities of sugars" src="https://github.com/user-attachments/assets/ac0a4406-a9e2-4983-838d-0d4fcc9e5b35" />
) 

### 2. Mean NADH Percentage Analysis
*Statistical comparison of metabolic output highlighting standard deviation across samples.*
![Bar Chart](<img width="524" height="428" alt="Mean baseline NADH percentage" src="https://github.com/user-attachments/assets/c633fd8a-9e0e-49d1-8a41-81ef7dac2752" />
)

### 3. Raw Confocal Processing
*Demonstration of the raw array data and segmentation at the 30s timepoint for comparison between Galactose and Glucose A.*
![Raw output vs Boolean masks](<img width="828" height="458" alt="Glucose A (30s)" src="https://github.com/user-attachments/assets/982fe5b0-bac1-4d3c-80cc-6342caed85b5" /> 
<img width="828" height="458" alt="Galactose A (30s)" src="https://github.com/user-attachments/assets/b46b12c3-c3a7-4ac5-bf9a-51a0466cf2f7" />
)
