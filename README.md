# GNSS Lab Report

**Authors**: Giorgia Moscato, Angelo Barbera, Alessandro Genova  
**Institution**: Politecnico di Torino  
**Date**: 2024

## Abstract
This report explores the Global Navigation Satellite System (GNSS), focusing on potential vulnerabilities such as spoofing attacks and signal interferences. Measurements were taken under varying conditions, followed by an analysis of the data using MATLAB. The resulting plots highlight the significant outcomes and their differences.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Methodology](#methodology)
   - [Filters](#filters)
     - [Multi-path Indicator](#multi-path-indicator)
     - [Carrier-to-Noise Density Ratio](#carrier-to-noise-density-ratio)
     - [Constellation Type](#constellation-type)
3. [Analysis](#analysis)
   - [Open Sky](#open-sky)
   - [Indoor](#indoor)
   - [Car](#car)
   - [Walking](#walking)
   - [Airplane](#airplane)
4. [Spoofing](#spoofing)
   - [Spoofing without Delay](#spoofing-without-delay)
   - [Spoofing with Delay](#spoofing-with-delay)
5. [Interference](#interference)
6. [Conclusion](#conclusion)
7. [References](#references)

---

## Introduction
The need for accurate positioning has been present throughout human history, evolving into the sophisticated GNSS technology we use today. This report investigates GNSS measurements in various conditions and demonstrates how signal quality and positioning accuracy are affected by factors such as multipath, signal strength, and environmental interferences.

## Methodology
We collected GNSS data using the GNSSLogger app on Android smartphones. The data were processed using MATLAB scripts, where different filters were applied to analyze the data. The filters allow us to select only the data that satisfies specific constraints.

### Filters

#### Multi-path Indicator
This filter identifies satellite signals affected by reflection or refraction (multi-path), which can cause inaccuracies. However, in our datasets, we couldn't detect multi-path due to smartphone antenna limitations.

#### Carrier-to-Noise Density Ratio
The C/N0 filter selects satellites based on signal strength, helping remove low-accuracy measurements. Surprisingly, we found that keeping weaker signals can sometimes provide more accurate positioning in certain environments.

#### Constellation Type
This filter selects specific GNSS satellite constellations, such as GPS or Galileo. In our tests, GPS was the only operational constellation due to software limitations.

## Analysis

### Open Sky
In ideal conditions (open sky), the GNSS receiver recorded stable signals, with minimal error in position estimation. The best 50% of estimates fell within a 3.2-meter radius.

### Indoor
Indoor measurements show a significant decline in accuracy, with errors up to 30 meters due to poor satellite visibility and signal reflection. The horizontal dilution of precision (HDOP) was unstable, leading to large variations in position estimates.

### Car
During the car test, signal quality varied, especially in tunnels where satellite signals were blocked. The horizontal speed was consistent with highway speeds, and HDOP remained stable in open areas.

### Walking
Walking measurements revealed variations in satellite visibility, leading to unreliable position estimates. HDOP values were higher, indicating less accurate positioning.

### Airplane
In the airplane scenario, positioning worked only when the receiver was near the window. The recorded speed and signal strength were consistent with the airplane's actual cruising speed.

## Spoofing

### Spoofing without Delay
We simulated a spoofing attack by altering the receiver’s location far from its real position. The pseudorange values showed significant changes, indicating successful spoofing detection.

### Spoofing with Delay
Introducing a 5-millisecond delay in the spoofed signal caused a noticeable peak in the pseudorange values. This delay can serve as an indicator of a spoofing attack.

## Interference
Measurements near interference sources showed a drop in signal-to-noise ratio, similar to indoor environments. The interference caused significant positioning errors due to weak satellite signals.

## Conclusion
The GNSS measurements revealed the impact of environmental conditions on positioning accuracy. We also examined spoofing attacks and their effects on pseudorange values. Power-saving modes in smartphones added further complexity to measurement consistency, and interference sources greatly degraded accuracy. These findings provide insight into the challenges of GNSS reliability and potential improvements.

---

This repository includes the full report and relevant MATLAB code for processing GNSS data. Follow the instructions in the report to replicate the results and perform your own GNSS measurements using GNSSLogger and MATLAB.
