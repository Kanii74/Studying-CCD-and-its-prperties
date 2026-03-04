# CCD Characterization and Analysis

This repository contains the work carried out as part of the **ES431 Astronomy Laboratory** at the **Indian Institute of Space Science and Technology (IIST)**.

The objective of this laboratory exercise was to study the **performance and behaviour of a Charge-Coupled Device (CCD)** used for astronomical observations. The experiment involved acquiring CCD data using the **SBIG ST-7XE camera equipped with a KAF0401E CCD detector**, followed by detailed analysis using **IRAF** and additional data analysis tools.

The study focuses on measuring key CCD parameters including:

- Bias Level  
- Read Noise  
- Dark Current  
- Linearity  
- Gain  
- Charge Transfer Efficiency (CTE)

These parameters determine the **noise behaviour, signal response, and overall performance of the CCD detector**, which are crucial for accurate astronomical observations.

---

# Repository Contents

| File | Description |
|-----|-------------|
| CCD Lab Report Kanishk SC20B152.pdf | Complete lab report describing the CCD experiment, data analysis and results |
| CCD_Characterization_Analysis (2).pdf | Detailed CCD data reduction and analysis procedures |
| CCD_LAB.pdf | Laboratory instructions and theoretical background |
| CCD_LAB_IRAF-Analysis.pdf | IRAF workflow used for CCD data reduction |
| README.md | Documentation of the project |

---

# Background

A **Charge-Coupled Device (CCD)** is a semiconductor detector widely used in astronomy for imaging faint sources. The detector consists of an array of light-sensitive pixels that convert incoming photons into electrons via the **photoelectric effect**.

The CCD operates through four main stages:

### Photon Detection
Incident photons generate electron–hole pairs in the silicon detector.

### Charge Storage
The generated electrons are stored in potential wells corresponding to individual pixels.

### Charge Transfer
The stored charge is transferred across the CCD pixel grid during readout.

### Signal Readout
The charge is converted into voltage and digitized into **Digital Numbers (DN)** by an Analog-to-Digital Converter (ADC).

CCD detectors provide **high sensitivity, good linearity, and low noise**, making them ideal for astronomical imaging.

---

# Experimental Setup

The experiment used the following hardware and software components.

## Detector System

- **Camera:** SBIG ST-7XE  
- **CCD Chip:** KAF0401E  
- **Detector Type:** Scientific CCD  
- **Operating Temperature:** ~5°C

## Software

- CCD data acquisition: **CCDops**
- Data reduction: **IRAF**
- Data visualization and plotting: **Python**

The CCD camera was connected to a laboratory computer, and exposures were taken under controlled conditions to measure detector performance.

---

# Data

This section summarizes the measurements obtained during the CCD characterization experiment.

---

## Bias Level Measurements

Bias frames were obtained at different operating temperatures to determine the electronic offset of the CCD.

| File Name | Temperature (°C) | Bias Level (DN) |
|---|---|---|
| Temperature_5_Bias_1.fits | 5 | 106.3 |
| Temperature_5_Bias_2.fits | 5 | 107.6 |
| Temperature_5_Bias_3.fits | 5 | 107.6 |
| Temperature_5_Mbias.fits | 5 | 107.2 |
| Temperature_Minus_0.23_Bias.fits | -0.23 | 105.3 |
| Temperature_10.27_Bias.fits | 10.27 | 105.7 |
| Temperature_15.45_Bias.fits | 15.45 | 107.3 |
| Temperature_Minus_4.82_Bias.fits | -4.82 | 106.0 |
| Temperature_5.33_Bias.fits | 5.33 | 105.3 |
| Temperature_Minus_8.13_Bias.fits | -8.13 | 105.9 |

---

## Read Noise Measurements

Read noise was determined from dark frames taken with the CCD shutter closed.

| File Name | Read Noise (DN) |
|---|---|
| 0.5s_Frame_1.fits | 6.468 |
| 0.5s_Frame_2.fits | 6.459 |
| 0.5s_Frame_3.fits | 6.465 |
| RMS at 0.5s | 6.464 |
| 1.0s_Frame_1.fits | 6.465 |
| 1.0s_Frame_2.fits | 6.467 |
| 1.0s_Frame_3.fits | 6.468 |
| RMS at 1.0s | 6.467 |
| 3.0s_Frame_1.fits | 6.499 |
| 3.0s_Frame_2.fits | 6.495 |
| 3.0s_Frame_3.fits | 6.499 |
| RMS at 3.0s | 6.498 |

---

## Dark Current vs Exposure Time

| Integration Time (s) | Dark Current (DN) |
|---|---|
| 1 | -1.292 |
| 5 | -2.585 |
| 10 | -3.339 |
| 20 | 2.455 |
| 50 | 3.467 |
| 100 | 4.811 |
| 200 | 15.23 |
| 500 | 40.77 |

---

## Dark Current vs Temperature

| Temperature (°C) | Dark Noise (DN) |
|---|---|
| -8.15 | 0.9147 |
| -4.85 | 0.3506 |
| -0.26 | 5.045 |
| 5.31 | 6.222 |
| 10.22 | 10.67 |
| 15.43 | 40.92 |
| 19.76 | 100.48 |

---

## Linearity Measurements

| Exposure Frame | Mean Counts (DN) |
|---|---|
| bs_cr_linear_1s | 2835.05 |
| bs_cr_linear_3s | 8204.52 |
| bs_cr_linear_5s | 13666 |
| bs_cr_linear_7s | 19350.1 |
| bs_cr_linear_10s | 27520.3 |
| bs_cr_linear_12s | 33473.1 |
| bs_cr_linear_15s | 41348.8 |
| bs_cr_linear_17s | 46211.6 |
| bs_cr_linear_20s | 52790.3 |
| bs_cr_linear_22s | 56753.8 |
| bs_cr_linear_24s | 59566.5 |
| bs_cr_linear_26s | 61962 |
| bs_cr_linear_28s | 62822.2 |

---

## Gain Calculation Data

| Mean (DN) | Variance (DN²) |
|---|---|
| 2785.05 | 912.159 |
| 8254.52 | 3121.36 |
| 13816 | 5439.37 |
| 19500.1 | 8324.14 |
| 27370.3 | 12889.8 |
| 33523.1 | 17144.4 |
| 41498.8 | 22736.6 |
| 46061.6 | 25098.9 |

Slope ≈ **0.58**

Gain:

```
g ≈ 1 / 0.58 ≈ 1.72 e⁻ / ADU
```

---

## Charge Transfer Efficiency (CTE)

| Pixel | DNp | DNp+1 | CTE |
|---|---|---|---|
| 121 | 9480 | 33 | 99.9971% |
| 331 | 5077 | 114 | 99.9932% |
| 485 | 12720 | 51 | 99.9992% |
| 582 | 6065 | 21 | 99.9994% |
| 716 | 6963 | 26 | 99.9996% |

---

# CCD Characterization

From the measurements, several key CCD characteristics were determined.

- **Bias Level:** ~106 DN  
- **Read Noise:** ~6.48 DN  
- **Gain:** ~1.72 e⁻ / ADU  
- **Linearity Range:** Up to ~17 seconds exposure  
- **Charge Transfer Efficiency:** ~99.99%

These parameters confirm that the detector behaves as expected for a scientific CCD used in astronomical imaging.

---

# Data Reduction Workflow (IRAF)

The CCD data were processed using the **IRAF astronomical data reduction package**.

The workflow involved:

1. Converting images to `.fits` format  
2. Removing cosmic ray hits  
3. Checking bias drift  
4. Creating a master bias frame  
5. Performing bias subtraction  
6. Measuring statistics using `imstat`  
7. Determining dark current and read noise  
8. Plotting detector response and estimating gain

IRAF tools used:

```
cosmicrays
imstat
imcombine
imarith
```

---

# Results Summary

| Parameter | Measured Value |
|---|---|
| Bias Level | ~106 DN |
| Read Noise | ~6.48 DN |
| Gain | ~1.72 e⁻ / ADU |
| Linearity Range | Up to ~17 s |
| Charge Transfer Efficiency | ~99.99% |

These results demonstrate that the CCD performs reliably and exhibits the expected behaviour for a scientific imaging detector.

---

# Conclusion

In this laboratory experiment, the performance characteristics of the **KAF0401E CCD detector** were studied through systematic measurements and analysis.

The study demonstrated:

- Stable bias levels  
- Low read noise  
- Strong temperature dependence of dark current  
- Linear detector response within a defined dynamic range  
- Accurate gain determination  
- High charge transfer efficiency

Understanding these detector properties is essential for **precision astronomical imaging**, as they directly affect photometric accuracy, calibration procedures, and noise performance.

This experiment provided practical experience in **CCD detector physics, astronomical instrumentation, and data reduction using IRAF**.
