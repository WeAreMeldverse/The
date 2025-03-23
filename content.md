# :memo: Classical Workflow

```

+---------------------------------------------------+
|             Video Ingestion                       |
|     (cv2.VideoCapture from SSD/cloud storage)     |
+----------------------+----------------------------+
                       |  
                       v  
+----------------------+----------------------------+
|            Frame Extraction                       |
|     (Read frames, convert to grayscale)           |
+----------------------+----------------------------+
                       |
                       v
+----------------------+----------------------------+
|       Preprocessing & Enhancement                 |
| (Grayscale Conversion, Gaussian Blur, Frame Diff) |
+----------------------+----------------------------+
                       |
          +------------+-------------+
          |                          |
          v                          v
+----------------------+   +---------------------------+
|   Blob Detection     |   |  Optional Analysis        |
| (Labeling & regionprops)| (Additional filtering)   |
+----------------------+   +---------------------------+
          |                          |
          +------------+-------------+
                       |
                       v
+----------------------+----------------------------+
|   Filtering & Blob Merging                        |
| (Area filtering, Confidence check,                |
|  Bounding Box & Euclidean Distance)               |
+----------------------+----------------------------+
                       |
                       v
+----------------------+----------------------------+
|       Classical Tracking                          |
| (Kalman Filter & Hungarian Algorithm for          |
|  data association)                                |
+----------------------+----------------------------+
                       |
          +------------+-------------+
          |                          |
          v                          v
+----------------------+   +---------------------------+
|   Post-Processing    |   | Visualization & Video     |
| (CSV Logging & Data  |   | Compilation (Plots, Graphs)|
|  Export)             |   |                           |
+----------------------+   +---------------------------+
```


# :memo: Machine Learning

```
+---------------------------------------------------+
|             Video Ingestion                       |
|     (cv2.VideoCapture from SSD/cloud storage)     |
+----------------------+----------------------------+
                       |  
                       v  
+----------------------+----------------------------+
|            Frame Extraction                       |
|     (Read frames, convert to grayscale)           |
+----------------------+----------------------------+
                       |
                       v
+----------------------+----------------------------+
|       Preprocessing & Enhancement                 |
| (Grayscale Conversion, Noise Reduction,           |
|  Frame Differencing, Thresholding, Morph Ops)     |
+----------------------+----------------------------+
                       |
                       v
+----------------------+----------------------------+
|   Data Preparation & Annotation                   |
| (Manual Labeling in COCO JSON Format)             |
+----------------------+----------------------------+
                       |
                       v
+----------------------+----------------------------+
|         Dataset Splitting                         |
| (Partition into Train, Validation, Test sets)     |
+-----------+----------+-----------+
           |                      |
           v                      v
+----------------------+   +---------------------------+
|   Model Training     |   | Validation & Testing      |
| (Detectron2, Faster  |   | (Metrics Evaluation)      |
|  R-CNN, Checkpointing)|  |                           |
+-----------+----------+   +---------------------------+
           |                      
           +----------+---------------+
                      |
                      v
+----------------------+----------------------------+
|         Inference                                |
| (DefaultPredictor, Confidence Threshold, NMS)    |
+----------------------+----------------------------+
                      |
                      v
+----------------------+----------------------------+
|        ML-Based Tracking                         |
| (DeepSORT Integration for robust tracking)       |
+----------------------+----------------------------+
                      |
                      v
+----------------------+----------------------------+
|      Post-Processing & Visualization             |
| (Drawing Boxes, CSV Generation, Video Compilation) |
+---------------------------------------------------+

```
