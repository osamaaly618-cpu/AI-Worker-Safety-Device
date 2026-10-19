# AI Worker Safety Device
### ESP32-S3 + MPU6050 | Embedded Human Activity Recognition

An embedded activity-recognition project exploring how inertial sensor data can help identify everyday movements and transitions. The goal is to build a practical foundation for worker-safety and movement-monitoring applications on resource-constrained hardware.

> **Project status:** Experimental / prototype. This repository is a public project overview and documentation space. It intentionally does not include private raw recordings, the full training dataset, trained model weights/headers, or internal experiment artifacts.

## Highlights

- **Embedded platform:** ESP32-S3
- **Motion sensor:** MPU6050 accelerometer and gyroscope
- **Inference target:** On-device activity classification
- **Activity categories explored:** walking, running, stairs up/down, crouching, picking, standing/sitting states, and transitions
- **Engineering focus:** sensor-data quality, windowed time-series classification, model evaluation, and deployment constraints

## System overview

1. The MPU6050 captures accelerometer and gyroscope measurements.
2. Firmware collects sensor samples and prepares time windows.
3. A trained classifier predicts an activity category.
4. The prediction can be used by a larger monitoring or safety workflow.

The details of preprocessing, feature extraction, sampling-rate handling, and firmware integration are implementation-dependent and should be validated against the exact hardware and model version.

## Current engineering challenge

A key challenge is distinguishing **ordinary walking from stair ascent** when the movement is slow, short, or performed with a limited step pattern. This is a useful reminder that aggregate accuracy alone does not establish real-world reliability: evaluation should include recording-level splits, per-class metrics, and confusion analysis, followed by physical-device testing.

## Repository scope

This public repository is intended to communicate the project, its architecture, limitations, and ownership terms. It does **not** publish the private training recordings, full dataset, model artifact, or internal training/evaluation files.

If you are reviewing this project for collaboration or recruitment, please use the overview here as a project summary rather than as a claim of production readiness.

## Validation status

- Prototype research and development
- Model performance depends on the dataset, recording conditions, sensor placement, and firmware preprocessing
- Real-world safety use requires additional validation, robustness testing, and a clearly defined failure-handling strategy
- No safety-critical or medical use is claimed

## Intellectual property and permissions

Copyright © 2026 the project owner. **All rights reserved.** Unless a file explicitly states otherwise, viewing this repository does not grant permission to copy, redistribute, modify, train on, or commercially use the project materials. See [NOTICE](NOTICE.md).

## Contact

For technical discussion or collaboration, please contact the repository owner through their GitHub profile.
