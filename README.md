# GuideWay AI: Real-Time Object Detection & Depth-Estimation Assistive Navigation System for the Visually Impaired

Intellectual Property Notice: The underlying source code for this architecture is maintained within a secure, private repository to safeguard proprietary algorithms and patent-pending frameworks. This repository serves as a public architectural showcase and technical specification sheet for hiring engineering managers.

---

## 💡 Patent Milestone
* **Status:** Official Indian Invention Patent Published
* **Core Innovation:** A unified, low-latency computational framework combining multi-class object localization with monocular depth maps over a single, non-stereoscopic camera lens.

---

## 🛠️ System Architecture & How It Works
GuideWay AI is designed as a high-frequency situational awareness loop for visually impaired users. Instead of relying on expensive, heavy hardware arrays like LiDAR or stereoscopic depth sensors, the system extracts precise spatial coordinates using standard video capturing devices.

[Live Camera Feed]
│
▼
[Python Multithreaded Ingestion Engine]
│
├──► Thread 1: YOLOv8 Pipeline ──► Object Classification & Bounding Boxes
└──► Thread 2: MiDaS Pipeline  ──► Spatial Depth Mapping & Matrix Calculation
│
▼
[Coordinate Fusion & Distance Solver] ──► Real-time Proximity Calculation
│
▼
[High-Priority Auditory Feedback Alert Engine]

1. **Ingestion & Parallel Processing:** A Python-based ingestion module splits incoming camera frames simultaneously into dual processing pipelines using hardware-accelerated multithreading to bypass system bottlenecks.
2. **Object Recognition:** Thread 1 routes frames through a customized **YOLOv8** network to detect and label immediate environmental entities (e.g., stairs, vehicles, obstacles, pedestrians) with high confidence scores.
3. **Monocular Depth Estimation:** Thread 2 feeds frames into a **MiDaS** deep learning model. The model computes relative inverse depth maps, turning a flat 2D frame into a dense array of spatial mathematical values.
4. **Data Fusion & Spatial Solving:** The system samples pixel regions inside the YOLOv8 bounding boxes and cross-references them with the MiDaS depth matrices to accurately solve for distance parameters in real time.
5. **Alert Logic:** If an object's calculated proximity falls below a safety threshold, a priority-weighted sound or voice notification loop triggers to alert the user instantly.

---

## 🧮 Tech Stack & Engineering Concepts
* **Language:** Python
* **Deep Learning Frameworks:** PyTorch, TensorFlow
* **Computer Vision Libraries:** OpenCV, YOLOv8, MiDaS
* **Core Computer Science Concepts:** Asynchronous Multithreading, Computer Vision Pipelines, Spatial Matrix Transformations, Sensor Data Fusion.

---

## 🎯 Key Engineering Performance Metrics
* **Processing Latency:** Sub-30ms model inference loop, allowing real-time navigation at normal human walking speeds.
* **Hardware Efficiency:** Optimized model weight distribution to allow execution on lower-power edge devices without thermal throttling.
* **Distance Accuracy:** High mathematical correlation between calculated monocular metrics and physical target distances within a 0.5m to 5m navigational radius.
