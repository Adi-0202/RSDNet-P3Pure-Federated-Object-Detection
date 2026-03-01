# RSDNet-P3Pure

## A FLOPs-Controlled Lightweight Federated Object Detection Framework for Real-Time Edge-Based Autonomous Driving

🚀 Official Research Repository

---

## 📌 Overview

RSDNet-P3Pure is a novel lightweight object detection architecture designed for federated learning and real-time edge deployment in autonomous driving systems.

Unlike conventional YOLO-based detectors that allocate heavy computation at high-resolution feature maps, RSDNet-P3Pure introduces a resolution-selective computation strategy that eliminates unnecessary high-resolution convolutional operations and reallocates representational capacity toward semantically deeper feature stages.

This design enables improved detection performance while significantly reducing computational complexity, making the framework suitable for distributed, privacy-preserving federated learning environments and edge devices.

The framework is rigorously evaluated under both IID and Non-IID data distributions using the KITTI and BDD100K datasets.

---

## 🧠 Key Contributions

- ✅ 33% parameter reduction compared to YOLOv8n baseline  
- ✅ Strict FLOPs-controlled feature fusion neck  
- ✅ Resolution-selective P3 pure routing mechanism  
- ✅ Federated Learning-aware computational complexity modeling  
- ✅ Robust performance under Non-IID data distributions  
- ✅ Eigen-CAM-based explainable AI integration  
- ✅ Real-time edge deployment validation  

---

## 🏗 Architecture Highlights

- Depthwise separable convolutions for computational efficiency  
- C2f-based semantic feature aggregation  
- FLOPs-controlled feature pyramid restructuring  
- Removal of convolutional refinement at highest resolution scale (P3)  
- Anchor-free detection head with Distribution Focal Loss  
- Federated Averaging (FedAvg) aggregation framework  

---

## 📊 Experimental Setup

### Datasets

- **KITTI** – Evaluated under IID federated distribution  
- **BDD100K** – Evaluated under Non-IID federated distribution  

### Federated Learning Configuration

- 3 distributed clients  
- 5 communication rounds  
- 5 local training epochs per round  
- FedAvg server-side aggregation  
- No raw data sharing  

### Edge Deployment Validation

- Raspberry Pi 5 (NCNN backend)  
- NVIDIA Jetson Orin Nano (INT8 TensorRT optimization)  

---

## 📈 Performance Summary

| Model | Dataset | mAP@0.5 | mAP@0.5-0.95 | Parameters (M) |
|--------|---------|----------|--------------|----------------|
| YOLOv8n (Baseline) | KITTI | 70.6% | 45.4% | 3.01 |
| RSDNet-P3Pure | KITTI | 77.2% | 49.7% | 2.02 |
| YOLOv8n (Baseline) | BDD100K | 30.2% | 16.8% | 3.01 |
| RSDNet-P3Pure | BDD100K | 41.3% | 23.3% | 2.02 |

The proposed framework consistently outperforms the baseline while maintaining reduced model complexity and improved federated training efficiency.

---

## 🔬 Federated Learning Objective

The global optimization objective minimizes the aggregated empirical risk across distributed clients:

L(w) = Σ (Nc / N) Lc(w)

where:
- Nc = number of samples at client c  
- N = total samples  
- Lc(w) = local detection loss  

Federated parameter aggregation is performed via standard FedAvg across communication rounds.

---

## 📂 Repository Structure

```
RSDNet-P3Pure/
│
├── paper/           # Research manuscript (PDF)
├── docs/            # Architecture diagrams and visualizations
├── configs/         # Configuration files (to be released)
├── experiments/     # Experimental logs and analysis
├── LICENSE
└── README.md
```

---

## 🔒 Code Availability

The source code and trained models are currently confidential due to ongoing research review and publication process.

The complete implementation and reproducibility artifacts will be released upon publication acceptance.

Unauthorized redistribution is prohibited at this stage.

---

## 👨‍💻 Author

**Aditya S, Ashwin Naresh M**  
Amrita Vishwa Vidyapeetham  
Coimbatore, India  

---

## 📧 Contact

For research collaboration, academic discussions, or technical queries:

[adityasureshofficial1010@gmail.com]

---

## ⭐ Acknowledgment

This research explores the intersection of lightweight deep learning architectures, federated optimization, and edge intelligence for scalable autonomous perception systems.