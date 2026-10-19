# High-Level Architecture

This diagram shows the public-facing system flow only. It intentionally omits private model internals, preprocessing details, training code, and dataset information.

```mermaid
flowchart LR
    A[MPU6050 sensor] --> B[ESP32-S3 sample collection]
    B --> C[Time-window preparation]
    C --> D[On-device activity classifier]
    D --> E[Predicted activity]
    E --> F[Application or monitoring logic]
```

The system is an experimental prototype. Real-world performance must be validated on the target hardware and under representative movement conditions.
