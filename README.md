# YOLO Variants for Satellite Image Object Detection

This repository provides a comprehensive analysis of YOLO (You Only Look Once) models for detecting objects in satellite imagery. The evaluation includes comparisons of different YOLO architectures, highlighting their strengths and weaknesses.

---

## 1. Introduction

Satellite imagery is a valuable resource for tasks such as urban planning, disaster response, and traffic monitoring. Accurate object detection in such images is crucial. YOLO-based models are well-suited for these applications due to their balance of speed and accuracy. This project evaluates several YOLO variants, including architectural enhancements, for their performance on satellite images.

---

## 2. Models Evaluated

### YOLOv5 Variants
- **Base YOLOv5:** A balanced model offering moderate precision and recall.
- **YOLOv5 with C3HB:** Features enhanced layers for better recall and mAP at the cost of increased complexity.

### YOLOv7 Variants
- **Base YOLOv7:** Highly optimized for speed and accuracy.
- **YOLOv7-Transformer-HorNet:** Incorporates Transformer and Hornet attention mechanisms for contextual understanding.
- **YOLOv7-C3C2-SPPFCSPC:** Features advanced modules for better feature aggregation.
- **YOLOv7-MobileOne:** Lightweight, mobile-friendly variant optimized for resource-constrained environments.

### YOLOv8 (Ultralytics)
- A lightweight model with only 3M parameters, suitable for real-time applications.

### YOLOv9 Base
- A robust model with advanced feature extraction capabilities and a high parameter count.

---

## 3. Dataset and Training Setup

- **Images:** 272 satellite images.
- **Classes:** Includes airliner, boat, bus, car, long vehicle, other, pushback truck, stair truck, truck, and van.
- **Framework:** PyTorch and Ultralytics.
- **Metrics Evaluated:**
  - **Precision (P):** Fraction of correct positive predictions.
  - **Recall (R):** Fraction of actual positives detected.
  - **mAP@0.5:** Average precision at IoU threshold 0.5.
  - **mAP@0.5:0.95:** Average precision across multiple IoU thresholds.

---

## 4. Results Summary

The following metrics are evaluated for each model:
- Precision (P)
- Recall (R)
- mAP@0.5
- mAP@0.5:0.95

Please refer to the tables below for detailed results.


## Overall Model Comparison

| Model                          | Precision (P) | Recall (R) | mAP@0.5 | mAP@0.5:0.95 |
|--------------------------------|---------------|------------|---------|--------------|
| **YOLOv5 Base**                | 0.721         | 0.561      | 0.587   | 0.419        |
| **YOLOv5 with C3HB**           | 0.556         | 0.689      | 0.670   | 0.493        |
| **YOLOv7 Base**                | 0.678         | 0.716      | 0.728   | 0.567        |
| **YOLOv7-Transformer-HorNet**  | 0.729         | 0.547      | 0.565   | 0.381        |
| **YOLOv7-C3C2-SPPFCSPC**       | 0.717         | 0.521      | 0.580   | 0.397        |
| **YOLOv7-MobileOne**           | 0.655         | 0.460      | 0.483   | 0.289        |
| **YOLOv8 Ultralytics**         | 0.637         | 0.690      | 0.692   | 0.529        |
| **YOLOv9 Base**                | 0.682         | 0.550      | 0.678   | 0.516        |


## Class-Wise Performance Metrics

| Class              | YOLOv5 P | YOLOv5 R | YOLOv5 mAP@0.5 | YOLOv5+C3HB P | YOLOv5+C3HB R | YOLOv5+C3HB mAP@0.5 | YOLOv7 P | YOLOv7 R | YOLOv7 mAP@0.5 | YOLOv7-Trans P | YOLOv7-Trans R | YOLOv7-Trans mAP@0.5 | YOLOv7-C3C2 P | YOLOv7-C3C2 R | YOLOv7-C3C2 mAP@0.5 | YOLOv7-MobileOne P | YOLOv7-MobileOne R | YOLOv7-MobileOne mAP@0.5 | YOLOv8 P | YOLOv8 R | YOLOv8 mAP@0.5 | YOLOv9 P | YOLOv9 R | YOLOv9 mAP@0.5 |
|--------------------|----------|----------|----------------|---------------|---------------|----------------------|----------|----------|----------------|----------------|----------------|----------------------|---------------|---------------|----------------------|-------------------|-------------------|--------------------------|----------|----------|----------------|----------|----------|----------------|
| **All**           | 0.721    | 0.561    | 0.587          | 0.556         | 0.689         | 0.670                | 0.678    | 0.716    | 0.728          | 0.729          | 0.547          | 0.565                | 0.717         | 0.521         | 0.580                | 0.655             | 0.460             | 0.483                  | 0.637    | 0.690    | 0.692          | 0.682    | 0.550    | 0.678          |
| **Airliner**      | 0.853    | 0.931    | 0.940          | 0.852         | 0.958         | 0.958                | 0.861    | 0.986    | 0.978          | 0.809          | 0.931          | 0.928                | 0.782         | 0.917         | 0.928                | 0.644             | 0.667             | 0.662                  | 0.846    | 0.972    | 0.965          | 0.851    | 0.972    | 0.973          |
| **Boat**          | 0.795    | 0.833    | 0.880          | 0.808         | 0.739         | 0.854                | 0.862    | 0.799    | 0.885          | 0.816          | 0.908          | 0.918                | 0.862         | 0.595         | 0.844                | 0.632             | 0.909             | 0.880                  | 0.725    | 0.956    | 0.910          | 0.940    | 0.689    | 0.901          |
| **Bus**           | 0.451    | 0.655    | 0.568          | 0.604         | 0.929         | 0.893                | 0.832    | 0.905    | 0.920          | 0.460          | 0.679          | 0.642                | 0.554         | 0.893         | 0.834                | 0.547             | 0.655             | 0.661                  | 0.715    | 0.798    | 0.865          | 0.839    | 0.714    | 0.881          |
| **Car**           | 0.650    | 0.826    | 0.821          | 0.728         | 0.822         | 0.836                | 0.741    | 0.866    | 0.874          | 0.634          | 0.772          | 0.763                | 0.584         | 0.822         | 0.724                | 0.579             | 0.757             | 0.700                  | 0.672    | 0.851    | 0.824          | 0.823    | 0.687    | 0.839          |
| **Long Vehicle**  | 0.646    | 0.640    | 0.638          | 0.581         | 0.747         | 0.747                | 0.762    | 0.774    | 0.803          | 0.521          | 0.582          | 0.604                | 0.803         | 0.582         | 0.722                | 0.580             | 0.395             | 0.481                  | 0.695    | 0.753    | 0.759          | 0.709    | 0.637    | 0.745          |
| **Other**         | 1.000    | 0.000    | 0.0426         | 0.310         | 0.214         | 0.156                | 0.369    | 0.300    | 0.257          | 1.000          | 0.000          | 0.0523               | 1.000         | 0.000         | 0.0503               | 1.000             | 0.000             | 0.0535                 | 0.250    | 0.186    | 0.150          | 0.000    | 0.000    | 0.0718         |
| **Pushback Truck**| 1.000    | 0.000    | 0.0386         | 0.103         | 0.100         | 0.101                | 0.433    | 0.200    | 0.288          | 1.000          | 0.000          | 0.0152               | 1.000         | 0.000         | 0.0644               | 1.000             | 0.000             | 0.025                  | 0.621    | 0.250    | 0.280          | 0.477    | 0.100    | 0.304          |
| **Stair Truck**   | 0.585    | 0.538    | 0.641          | 0.508         | 0.769         | 0.635                | 0.643    | 0.739    | 0.661          | 0.797          | 0.410          | 0.523                | 0.387         | 0.513         | 0.465                | 0.466             | 0.157             | 0.312                  | 0.602    | 0.718    | 0.706          | 0.657    | 0.410    | 0.544          |
| **Truck**         | 0.641    | 0.473    | 0.601          | 0.516         | 0.780         | 0.721                | 0.639    | 0.795    | 0.796          | 0.648          | 0.492          | 0.595                | 0.603         | 0.242         | 0.466                | 0.625             | 0.417             | 0.498                  | 0.626    | 0.634    | 0.681          | 0.739    | 0.667    | 0.742          |
| **Van**           | 0.592    | 0.712    | 0.698          | 0.547         | 0.827         | 0.798                | 0.637    | 0.798    | 0.820          | 0.603          | 0.700          | 0.613                | 0.598         | 0.648         | 0.697                | 0.472             | 0.640             | 0.553                  | 0.622    | 0.787    | 0.777          | 0.787    | 0.625    | 0.781          |


---

## 5. Observations

### Strengths and Weaknesses
- **YOLOv5 Variants:** Base YOLOv5 balances efficiency and accuracy, while YOLOv5+C3HB improves recall and mAP with increased complexity.
- **YOLOv7 Variants:** Base YOLOv7 is highly effective, while Transformer-HorNet excels in contextual understanding. MobileOne is optimal for mobile deployment.
- **YOLOv8:** Lightweight and efficient, suitable for real-time scenarios.
- **YOLOv9 Base:** Offers the highest parameter count and advanced feature extraction capabilities.

### Recommendations
- **General Use:** YOLOv7 (Base) is recommended for its balance of speed and accuracy.
- **Rare Classes:** Models like YOLOv9 or YOLOv7-C3C2-SPPFCSPC may be further fine-tuned for detecting rare objects.

---

## 6. Future Work

- Investigate semi-supervised learning to improve rare object detection.
- Explore hybrid architectures for balancing efficiency and accuracy.
- Optimize models for edge and real-time deployments.

---

## 7. Contributions

This project demonstrates the capabilities of various YOLO architectures in satellite image object detection, providing insights into their practical applications.

