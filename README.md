The datasets and benchmark protocol for:

<div align="center">
<h1>
<b>
Few-Shot Referring Video Object Segmentation Datasets
</b>
</h1>
</div>


Few-Shot Referring Video Object Segmentation (FS-RVOS) aims to segment the object specified by a natural-language expression in a query video, given only a small number of annotated support samples. In contrast to conventional referring video object segmentation, FS-RVOS requires models to generalize to unseen object categories and establish reliable cross-video correspondence between query and support videos under limited supervision.

This repository provides the dataset splits, referring expressions, segmentation annotations, support-query metadata, and evaluation protocols used in:

> **RSCM: Reliable Support Construction Model for Few-Shot Referring Video Object Segmentation**
>
> Heng Liu<sup>1,*</sup>, Jiacheng Yao<sup>1</sup>, Pengfei Zhang<sup>1</sup>, and Yang Wang<sup>2</sup>
>
> <sup>1</sup> School of Computer Science and Technology, Anhui University of Technology, Ma'anshan 243032, China  
> <sup>2</sup> School of Computer Science and Information Engineering, Hefei University of Technology, Hefei 230601, China  
>
> <sup>*</sup> Corresponding author: Heng Liu

The repository includes four benchmarks: Mini-Ref-YouTube-VOS, Mini-Ref-SAIL-VOS, Mini-DAVIS, and Mini-MeViS. These benchmarks support category-disjoint few-shot evaluation, direct cross-domain evaluation, and multi-object referring video segmentation.

> **Note:** This repository provides datasets and benchmark protocols only. The implementation of RSCM will be released separately.

## Dataset Overview

| Dataset | Source Dataset | Main Purpose |
|---|---|---|
| Mini-Ref-YouTube-VOS | Ref-YouTube-VOS | Category-disjoint FS-RVOS evaluation |
| Mini-Ref-SAIL-VOS | SAIL-VOS | Direct cross-domain evaluation |
| Mini-DAVIS | Ref-DAVIS17 | Direct cross-domain evaluation on real-world videos |
| Mini-MeViS | MeViS | Multi-object and motion-centric evaluation |

### Mini-Ref-YouTube-VOS

Mini-Ref-YouTube-VOS is a category-disjoint FS-RVOS benchmark derived from Ref-YouTube-VOS. It contains 1,668 videos from 48 semantic categories, together with referring expressions and pixel-level object annotations.

The 48 categories are partitioned into four mutually exclusive groups, with 12 categories in each group. For Group-\(n\) evaluation, the 12 categories in Group-\(n\) are held out for testing, while the categories in the remaining three groups are used for training.

During testing, the query video and its candidate support pool are sampled from different videos belonging to the same held-out category.

### Mini-Ref-SAIL-VOS

Mini-Ref-SAIL-VOS is adapted from SAIL-VOS and is used for direct cross-domain evaluation. It contains challenging cases involving occlusion, shot transitions, large appearance variations, and cluttered backgrounds.

Models are directly evaluated on Mini-Ref-SAIL-VOS without target-domain training or fine-tuning.

### Mini-DAVIS

Mini-DAVIS is adapted from Ref-DAVIS17 and is used for direct cross-domain evaluation on real-world videos. It mainly contains single-object videos and a small number of same-category two-instance cases.

### Mini-MeViS

Mini-MeViS is adapted from MeViS under the FS-RVOS protocol. It contains multi-object scenes and motion-centric referring expressions, making it suitable for evaluating target disambiguation and temporal reasoning.

## Dataset Download

### Mini-Ref-YouTube-VOS and Mini-Ref-SAIL-VOS

Mini-Ref-YouTube-VOS and Mini-Ref-SAIL-VOS are publicly available from the dataset release of the following IJCV paper:

> **Few-Shot Referring Video Single- and Multi-Object Segmentation via Cross-Modal Affinity with Instance Sequence Matching**  
> Heng Liu, Guanghui Li, Mingqi Gao, Xiantong Zhen, Feng Zheng, and Yang Wang.  
> *International Journal of Computer Vision (IJCV), 2025.*

Please download the datasets from:

[Google Drive: Mini-Ref-YouTube-VOS and Mini-Ref-SAIL-VOS](https://drive.google.com/drive/folders/1ZdrQY8gKKEmMoJxP13ZZ5_Qrc4hGoZUj?usp=sharing)

[Google Drive: Mini-DAVIS and Mini-MeViS](https://drive.google.com/drive/folders/1q-3zaKZREesxM4tb9ycZw6wxlLeoc9dl?usp=drive_link)



## Directory Structure

After downloading and extracting the datasets, please organize them as follows:

```text
data
├─ Mini-Ref-YouTube-VOS
│  ├─ meta_expressions
│  ├─ train
│  │  ├─ Annotations
│  │  ├─ JPEGImages
│  │  └─ train.json
│  └─ splits
│     ├─ group1_train.json
│     ├─ group1_test.json
│     ├─ group2_train.json
│     ├─ group2_test.json
│     ├─ group3_train.json
│     ├─ group3_test.json
│     ├─ group4_train.json
│     └─ group4_test.json
├─ Mini-Ref-SAIL-VOS
│  ├─ meta_expressions
│  ├─ train
│  │  ├─ Annotations
│  │  ├─ JPEGImages
│  │  └─ train.json
│  └─ splits
├─ Mini-DAVIS
│  ├─ Annotations
│  ├─ JPEGImages
│  ├─ meta_expressions
│  └─ splits
└─ Mini-MeViS
   ├─ Annotations
   ├─ JPEGImages
   ├─ meta_expressions
   └─ splits
