# An Empirical Analysis of Anomaly Detection Model Paradigms under Heterogeneous IoMT Attack Traffic

This repository contains the code and paper for an undergraduate research project investigating anomaly detection in heterogeneous Internet of Medical Things (IoMT) networks. The study evaluates how different anomaly detection paradigms respond to diverse IoMT attack scenarios and analyzes the effect of traffic heterogeneity on detection behavior.

# Problem Statement

Hospital networks include a variety of IoMT devices with distinct traffic patterns. Centralized intrusion detection systems (IDS) typically aggregate traffic across devices, which can mask device-specific anomalies and reduce detection reliability.

This project examines how clustering similar IoMT device traffic and training cluster-specific anomaly detection models influences IDS performance. The focus is on empirical evaluation of model behavior, rather than on developing or comparing new models.

# Dataset

Experiments use the CICIoMT2024 dataset, which contains network flows from multiple IoMT devices commonly found in hospitals.

The dataset is used without modification, except for synthetic injection of anomalous flows to evaluate detection behavior under controlled scenarios.

Features include packet header statistics, transport-level flags, protocol indicators, traffic volume, packet size statistics, and temporal behaviors.

# Methodology

Train a global Isolation Forest model on all IoMT traffic.

Apply KMeans clustering to group flows with similar patterns.

Train cluster-specific Isolation Forest models on each cluster.

Inject anomalous flows (simulated attacks) and evaluate detection behavior.

Analyze anomaly scores, detection speed, and sensitivity across models and clusters.

# Key Findings

Cluster-specific models often detect anomalies in device traffic more quickly.

Some subtle anomalies are more prominent in cluster-aware models, while other anomalies are detected faster by the global model.

Both global and cluster-aware models have limitations when anomalies closely resemble normal traffic.

Traffic heterogeneity and modeling granularity significantly impact IDS behavior in hospital networks.

# Notes

All models are unsupervised; no labeled attack data is required.

Malicious traffic was synthetically generated for controlled evaluation.

This project was conducted as an independent undergraduate research study.
