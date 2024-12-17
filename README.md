**Project Proposal – Deep Learning (CS-GY 6953)**

**Team:** Sai Spoorthi Tammineni **(st5294)**

**Title:** Improving Accuracy and Efficiency in Deep Learning-based 3D Point Cloud Classification

**Problem Statement:** Point cloud data, a critical geometric data structure, poses significant challenges due to its irregular format, making it incompatible with traditional grid-based neural network architectures. Existing approaches often transform point clouds into regular 3D voxel grids or image collections, leading to excessive data volume and associated inefficiencies. There is a need for a neural network architecture that directly processes raw point clouds while preserving their permutation invariance and maintaining computational efficiency. Addressing this challenge can enable robust and effective applications in object classification, part segmentation, and scene semantic parsing, overcoming limitations of current methods and enhancing performance across various tasks.

**Literature Survey:** Traditional methods transform point clouds into regular 3D voxel grids or collections of images, causing high data redundancy and quantization artifacts. PointNet addresses these challenges by directly processing point clouds, preserving the permutation invariance of the input points \[1\]. Prior works like Volumetric CNNs and Multi-view CNNs require structured inputs such as voxel grids or images, which introduce inefficiencies for irregular data like point clouds \[2\]. PointNet employs symmetric functions (e.g., max pooling) to achieve permutation invariance, distinguishing it from sequence-based RNN methods or sorting-based approaches, which struggle with high-dimensional irregular data \[3\].

**Dataset:** <http://3dvision.princeton.edu/projects/2014/3DShapeNets/ModelNet10.zip>

**ModelNet40** is a widely used synthetic dataset for benchmarking 3D object classification tasks. It comprises **12,311 CAD models** categorized into **40 object classes**, including airplanes, chairs, sofas, and tables. Each object is represented as a uniformly sampled point cloud, derived from 3D mesh surfaces, and preprocessed to align at the origin and normalized to a unit sphere. The dataset is split into **9,843 samples** for training and **2,468 samples** for testing, making it a standard benchmark for evaluating the performance of 3D classification models.

**Model: PointNet** directly processes raw point cloud data using shared multi-layer perceptrons (MLPs) to extract features from individual points and a symmetric function (max pooling) to aggregate global features, ensuring permutation invariance. It includes a **T-Net module** to align input data and extracted features. PointNet is efficient, lightweight, and handles unordered, irregular point cloud data without transformations like voxelization, making it suitable for real-time applications in object classification, part segmentation, and scene semantic parsing. However, it struggles to capture local geometric relationships, limiting its performance on complex datasets. **VoxNet**, on the other hand, converts point clouds into voxel grids and leverages 3D convolutional neural networks (3D CNNs) to process this structured data. It extracts spatial features through convolutional and fully connected layers for classification, effectively capturing local and spatial relationships. While compatible with standard deep learning frameworks, VoxNet's voxelization process leads to high memory consumption and potential information loss, making it better suited for object detection and classification in structured 3D environments.

**Goal:** The goal of this project is to evaluate and compare the performance of PointNet and VoxNet for 3D point cloud classification tasks. Specifically, the project aims to achieve high classification accuracy, with a target of at least 95% accuracy on the ModelNet40 dataset, while analyzing the trade-offs in computational efficiency.

**References:**

\[1\] Charles R. Qi, Hao Su, Kaichun Mo, and Leonidas J. Guibas. "_PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation," arXiv:1612.00593._

\[2\] Hang Su, Subhransu Maji, Evangelos Kalogerakis, and Erik Learned-Miller. "_Multi-view Convolutional Neural Networks for 3D Shape Recognition," Proceedings of ICCV 2015._

\[3\] Daniel Maturana and Sebastian Scherer. "_VoxNet: A 3D Convolutional Neural Network for Real-Time Object Recognition," Proceedings of IROS 2015._
