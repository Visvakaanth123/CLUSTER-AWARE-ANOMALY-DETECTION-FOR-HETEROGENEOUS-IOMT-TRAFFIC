# Cluster-Aware Anomaly Detection for Heterogeneous IoMT Traffic

This repository contains the code and paper for an undergraduate research project
that studies intrusion detection in heterogeneous Internet of Medical Things (IoMT)
environments.

The project compares a traditional global intrusion detection system (IDS) with a
cluster-aware IDS approach using KMeans clustering and Isolation Forests.

---

## Problem Statement

Hospital networks contain many heterogeneous IoMT devices with distinct traffic
patterns. Most deployments rely on a single global IDS, which may fail to detect
device-specific attacks because anomalous behavior can be masked by normal traffic
from other devices.

This project investigates whether clustering similar IoMT device traffic and training
cluster-specific anomaly detection models improves detection performance.

---

## Dataset

Experiments use the **CCIoMT2024** dataset, which contains network traffic from multiple
IoMT devices commonly found in hospital environments.

The dataset is publicly available and was used without modification except for
synthetic injection of malicious flows for evaluation.

---

## Methodology

1. Train a **global Isolation Forest** model on all IoMT traffic
2. Apply **KMeans clustering** to group similar device traffic
3. Train a **cluster-specific Isolation Forest** on the selected device cluster
4. Compare detection speed and reliability between global and cluster-specific IDS models

## Results Summary

The cluster-specific IDS consistently detected malicious flows faster and more
reliably than the global IDS. Several attacks that were missed entirely by the global
model were detected by the cluster-aware approach within one or two detection windows.

---

## Notes

- This project uses **unsupervised learning** and does not rely on labeled attack data.
- Malicious traffic was synthetically generated to evaluate detection behavior.
- The work was conducted as an independent undergraduate research project.

---

## References

- F. T. Liu, K. M. Ting, and Z. Zhou, “Isolation Forest,” IEEE ICDM, 2008.
- CCIoMT2024 Dataset
