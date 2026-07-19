

<div align="center">
<h1>
<b>
RSCM: Reliable Support Construction Model for Few-Shot Referring Video Object Segmentation
</b>
</h1>
</div>



Few-Shot Referring Video Object Segmentation (FS-RVOS) aims to segment a language-referred object in a query video from only a few annotated support frames, including object masks and referring expressions. Existing methods often rely on compact foreground prototypes, direct support-query matching, indiscriminate multi-support aggregation, or randomly sampled support frames. These designs are vulnerable to incomplete target representations, background distractors, unreliable support injection, and unstable cross-video correspondence under occlusion, appearance variation, and complex motion.

In this paper, we propose RSCM, a Reliable Support Construction Model for FS-RVOS, which improves support utilization from the perspectives of support construction, prototype modeling, and support-query interaction. RSCM explicitly constructs foreground and background support prototypes to model target evidence and background counter-evidence. A support-guided prototype agent injects support priors into query features through gated residual adaptation. In addition, a query-aware multi-support aggregation mechanism derives a soft query prior and estimates frame-level and token-level reliability for adaptive support aggregation. We further introduce a reliability-weighted support selection strategy to construct a reliable support window from a category-specific candidate pool.

To facilitate research on FS-RVOS, we provide the benchmark data and evaluation protocols used in our experiments, including Mini-Ref-YouTube-VOS, Mini-Ref-SAIL-VOS, Mini-DAVIS, and Mini-MeViS. The datasets support category-disjoint few-shot evaluation, direct cross-domain evaluation, and multi-object referring video segmentation.

> **RSCM: Reliable Support Construction Model for Few-Shot Referring Video Object Segmentation**
>
> Heng Liu<sup>1,*</sup>, Jiacheng Yao<sup>1</sup>, Pengfei Zhang<sup>1</sup>, and Yang Wang<sup>2</sup>
>
> <sup>1</sup> School of Computer Science and Technology, Anhui University of Technology, Ma'anshan 243032, China  
> <sup>2</sup> School of Computer Science and Information Engineering, Hefei University of Technology, Hefei 230601, China  
>
> <sup>*</sup> Corresponding author: Heng Liu

> Paper: To be released.

## Data Preparation

Create a new directory named `data` to store all datasets.

1. Download Mini-Ref-YouTube-VOS and Mini-Ref-SAIL-VOS from the public release of the IJCV 2025 paper:

   [Google Drive: Mini-Ref-YouTube-VOS and Mini-Ref-SAIL-VOS](https://drive.google.com/drive/folders/1ZdrQY8gKKEmMoJxP13ZZ5_Qrc4hGoZUj?usp=sharing)

2. Download Mini-DAVIS and Mini-MeViS from:

   [Google Drive: Mini-DAVIS and Mini-MeViS](https://drive.google.com/drive/folders/1q-3zaKZREesxM4tb9ycZw6wxlLeoc9dl?usp=drive_link)

3. Extract all dataset packages into the `./data` directory.

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
