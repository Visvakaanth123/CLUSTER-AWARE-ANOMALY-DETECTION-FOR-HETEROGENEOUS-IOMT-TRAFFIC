# Empirical Analysis of Anomaly Detection Paradigms in Heterogeneous IoMT
This repository contains the code and methodology for an empirical study evaluating how different unsupervised machine learning paradigms interpret malicious behavior in diverse Internet of Medical Things (IoMT) environments.

# Research Overview
Hospitals rely on a vast array of heterogeneous IoMT devices (infusion pumps, wearable sensors, imaging systems), each with distinct communication protocols and traffic patterns. This study evaluates the response of three distinct algorithmic paradigms when tasked with detecting anomalies in aggregated, multi-device traffic:

Tree-based: Isolation Forest (IF) 

Boundary-based: One-Class SVM (OC-SVM) 

Density-based: Local Outlier Factor (LOF) 

# Dataset & Preprocessing
The analysis utilizes the CICIoMT2024 benchmark dataset.

Feature Engineering: Includes 46 statistical features covering packet headers, transport-level flags, protocol indicators, and temporal behavior .

Normalization: Features are standardized to ensure distance-based models (OC-SVM, LOF) are not biased by numeric ranges.

Unsupervised Training: All models are trained exclusively on benign traffic to simulate real-world deployment where attack labels are unavailable.

# Key Findings

Isolation Forest is superior for early-stage reconnaissance detection but struggles with subtle application-layer probes.

OC-SVM provides the highest overall sensitivity but suffers from "score saturation," making it difficult to prioritize high-severity alerts.

LOF is highly effective at identifying high-intensity volumetric spikes but is easily evaded by "low-and-slow" stealthy scans
