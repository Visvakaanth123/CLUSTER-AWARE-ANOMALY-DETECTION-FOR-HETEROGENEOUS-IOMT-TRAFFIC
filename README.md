# Cluster-Aware Anomaly Detection for Heterogeneous IoMT Traffic

This repository contains the code and paper for an undergraduate research project
that studies anomaly detection in heterogeneous Internet of Medical Things (IoMT) networks.

The project conducts an empirical evaluation of global vs. cluster-aware IDS configurations using Isolation Forests and KMeans clustering to analyze how modeling granularity affects anomaly detection behavior.

# Problem Statement

Hospital networks include a variety of IoMT devices with distinct traffic patterns.
Centralized intrusion detection systems (IDS) often aggregate traffic across devices, which can mask device-specific anomalies and reduce detection reliability.

This project investigates how grouping similar IoMT device traffic into clusters and training cluster-specific anomaly detection models influences IDS performance, with a focus on empirical evaluation rather than model comparison.

# Dataset

Experiments use the CCIoMT2024 dataset, which contains network traffic from multiple IoMT devices commonly found in hospitals.

The dataset was used without modification except for synthetic injection of anomalous flows to evaluate detection behavior under controlled conditions.

# Methodology

Train a global Isolation Forest model on all IoMT traffic.

Apply KMeans clustering to group flows with similar traffic patterns.

Train a cluster-specific Isolation Forest on the selected cluster.

Evaluate model responses to injected anomalous flows, analyzing detection speed, anomaly scores, and sensitivity.

# Key Findings

Cluster-specific models detect deviations in device traffic more quickly in many cases.

Some anomalous flows that remain subtle in the homogeneous model are more prominently reflected in anomaly scores under cluster-aware modeling, While some flows are detected quicker in the homogeneous model.

Both global and cluster-aware configurations have limitations depending on statistical similarity of anomalies to normal traffic.

These findings illustrate the impact of traffic heterogeneity and modeling granularity on IDS behavior in hospital networks.

# Notes

All models use unsupervised learning; no labeled attack data is required.

Malicious traffic was synthetically generated for controlled evaluation.

This work was conducted as an independent undergraduate research project.
