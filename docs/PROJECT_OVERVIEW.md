# Project Overview

## Objective

Explore inertial-sensor-based activity recognition on an ESP32-S3 using an MPU6050 accelerometer and gyroscope. The long-term application area is worker-safety and movement monitoring; this repository describes a prototype, not a certified product.

## High-level pipeline

```text
MPU6050
  -> timestamped accelerometer/gyroscope samples
  -> sampling and sensor-quality checks
  -> time-window preparation
  -> feature extraction / classifier input
  -> activity prediction
  -> application-level handling
```

Exact preprocessing and model details are intentionally not published in this overview.

## Activity classes explored

The project has investigated classes including:
- WALK and RUN
- STAIRS_UP and STAIRS_DOWN
- CROUCH and PICK
- STILL_STAND and STILL_SIT
- SIT_TO_STAND and STAND_TO_SITTING

Class definitions and transition boundaries should be documented consistently before collecting or labeling new recordings.

## Evaluation principles

For time-series activity recognition, random window-level splits can overstate generalization when neighboring windows from one recording appear in both training and evaluation. Prefer grouping by source recording or session, then report:
- overall accuracy and macro F1
- precision/recall per activity class
- a confusion matrix, especially WALK vs STAIRS_UP
- performance on recordings not used during training
- physical-device results under realistic sensor placement and movement conditions

A single aggregate score is not enough to establish readiness for safety-related use.

## Known challenge

Slow walking, walking in place, short steps, and small forward/backward movements can resemble stair ascent in inertial signals. Improvements should be evaluated in both directions:
- WALK predicted as STAIRS_UP
- STAIRS_UP predicted as WALK

Changes should be compared using the same recording groups and evaluation protocol wherever possible.

## Data and model policy

This public overview does not include private recordings, the complete training dataset, model binaries/headers, or internal experiment reports. Keep those in a private location unless the owner explicitly approves their release after a privacy, IP, and license review.
