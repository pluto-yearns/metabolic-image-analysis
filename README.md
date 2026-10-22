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
![Time Series Graph](images/image_22b79f.png) 

### 2. Mean NADH Percentage Analysis
*Statistical comparison of metabolic output highlighting standard deviation across samples.*
![Bar Chart](images/image_22b7a5.png)

### 3. Raw Confocal Processing
*Demonstration of the raw array data and segmentation at the 180s and 210s timepoints.*
![Confocal Output](images/image_22b767.jpg)
