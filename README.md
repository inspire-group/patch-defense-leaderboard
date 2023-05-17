# Leaderboard: Certifiable Robustness against Adversarial Patch Attacks

This repository provides a leaderboard for certifiable robustness against adversarial patch attacks.

Check out [our paper list and tutorials](https://github.com/xiangchong1/adv-patch-paper-list) for adversarial patch attacks and defenses! 



## About

For now, this leaderboard focuses on the setting of

1. Image classification task
   - For Object Detection, see the [ObjectSeeker paper](https://arxiv.org/abs/2202.01811).
   - For Semantic Segmentation, see [this paper](https://arxiv.org/abs/2209.05980).  
2. ImageNet dataset
3. One 2% square patch anywhere on the image
4. Prediction Recovery vs. attack detection (read this [explanation](https://github.com/xiangchong1/adv-patch-paper-list#robust-prediction-vs-attack-detection) for the difference between these two notions)

Stay tuned for future updates on different datasets and tasks :)

### Annotated attributes

We include the following properties of different defenses in this leaderboard.

1. **Defense name and publication venue**.
2. **Certified robust accuracy:** certified robust accuracy for a 2%-pixel square patch anywhere on the image. All leaderboards are sorted by certified robust accuracy
3. **Clean accuracy:** clean accuracy of the defended models
4. **Vanilla clean accuracy:** clean accuracy of vanilla undefended models (if the defense is built upon off-the-shelf models)
5. **Backbone:** the backbone used for each defense
6. **Comment:** additional comments for each defense, including SOTA results, defense parameters, special training recipes.
7. **Code:** most defenses have source code implemented by the authors or others

**Note:** We discuss more properties of different defenses in [another copy of leaderboards](https://docs.google.com/spreadsheets/d/1zDBg5AmpWq92c_MaSx6vq4FsOUnzu57i8aUuex2NT7Y/edit?usp=sharing) hosted on Google Sheet.

### Contributions

If you have new results and want to contribute to the leaderboard. Please submit a pull request or email me (Chong Xiang; cxiang@princeton.edu)

## Table of Contents

- [**Prediction Recovery**](#prediction-recovery)
- [**Attack Detection**](#attack-detection)

## Prediction Recovery

The prediction recovery defense requires the defense model to always predict/recover the robust label (without any abstention).

### ImageNet

|                                                              | certified robust accuracy | clean accuracy | vanilla clean accuracy | backbone                           | comment                                                      | code                                                    |
| ------------------------------------------------------------ | ------------------------- | -------------- | ---------------------- | ---------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------- |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 62.1                      | 83.9           | 84.8                   | ViT-B                              | **SOTA with known patch size**; k=6; trained with cutout     | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 61.6                      | 83.8           | 84.8                   | ViT-B                              | k=6                                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 59.8                      | 83.7           | 84.8                   | ViT-B                              | k=5; trained with masked images                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 59.4                      | 83.6           | 83.7                   | ViT-B                              | k=4; trained with masked images                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 56.1                      | 83.3           | 84.8                   | ViT-B                              | k=3; trained with masked images                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 53.8                      | 79.4           | 80.2                   | ResMLP-S                           | k=6; trained with masked images                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 53.1                      | 79.6           | 80.8                   | ResMLP-S                           | k=6                                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 53                        | 81.6           | 82.3                   | ResNet-50                          | k=6; trained with masked images                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [ViP](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7173_ECCV_2022_paper.php) (ECCV 2022) | 45.4                      | 74.1           |                                      | ViT-L (MAE)    | **SOTA with unknown patch size** (using a larger model MAE-Large); trained with [MAE](https://arxiv.org/abs/2111.06377); b=19; stride = 5  | [code](https://github.com/UCSC-VLAA/vit_cert) |
| [ViP](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7173_ECCV_2022_paper.php) (ECCV 2022) | 44.6                      | 73.6           |                                      | ViT-L (MAE)    |  b=19; stride = 10  | [code](https://github.com/UCSC-VLAA/vit_cert) |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 41.7                      | 78.58          | NA                     | ViT-B                              | **SOTA with unknown patch size**; b=37; progressively trained with pixel bands | NA                                                      |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 41.6                      | 81.1           | 82.8                   | ResNet-50                          | k=6                                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [ViP](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7173_ECCV_2022_paper.php) (ECCV 2022) | 41.4                      | 70.8           |     83.7                                 | ViT-B (MAE)    |  b=19; stride = 1  | [code](https://github.com/UCSC-VLAA/vit_cert) |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 40.79                     | 75.3           | NA                     | ViT-B                              | b=25; progressively trained with pixel bands                 | NA                                                      |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 40.72                     | 73.49          | NA                     | ViT-B                              | b=19; progressively trained with pixel bands                 | NA                                                      |
| [ViP](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7173_ECCV_2022_paper.php) (ECCV 2022) | 40.6                      | 70.4           |     83.7                                 | ViT-B (MAE)    |  b=19; stride = 5  | [code](https://github.com/UCSC-VLAA/vit_cert) |
| [ViP](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7173_ECCV_2022_paper.php) (ECCV 2022) | 49.8                      | 69.9           |     83.7                                 | ViT-B (MAE)    |  b=19; stride = 10  | [code](https://github.com/UCSC-VLAA/vit_cert) |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 38.3                      | 69.3           | NA                     | ViT-B                              | **SOTA with unknown patch size (with code)**; b=19           | [code](https://github.com/MadryLab/smoothed-vit)        |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 38.2                      | 73.2           | NA                     | ViT-B                              | b=37; trained with pixel bands                               | [code](https://github.com/MadryLab/smoothed-vit)        |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 36.9                      | 68.3           | NA                     | ViT-B                              | b=19; s=10; trained with pixel bands                         | [code](https://github.com/MadryLab/smoothed-vit)        |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 31.6                      | 63.5           | NA                     | ViT-S                              | b=19; trained with pixel bands                               | [code](https://github.com/MadryLab/smoothed-vit)        |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 30.06                     | 67.14          | NA                     | ViT-S                              | b=25; progressively trained with pixel bands                 | NA                                                      |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 29.74                     | 69.88          | NA                     | ViT-S                              | b=37; progressively trained with pixel bands                 | NA                                                      |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 28.85                     | 64.69          | NA                     | ViT-S                              | b=19; progressively trained with pixel bands                 | NA                                                      |
| [De-randomized  Smoothing](https://arxiv.org/abs/2002.10733) (NeurIPS 2020) (from the  [Smoothed ViT](https://arxiv.org/abs/2110.07719) ) | 28.1                      | 61.4           | NA                     | WRN-101-2                          | b=19; trained with pixel bands                               | [code](https://github.com/MadryLab/smoothed-vit)        |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 26                        | 54.6           | 56.5                   | BagNet-17                          | trained with masked features                                 | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 24.1                      | 60.4           | 63                     | BagNet-33                          | trained with masked features                                 | [code](https://github.com/inspire-group/PatchCleanser)  |
| [BagCert](https://arxiv.org/abs/2102.04154)  (ICLR 2021)     | 22.7                      | 45.3           | NA                     | BagNet-17                          |                                                              | NA                                                      |
| [BagCert](https://arxiv.org/abs/2102.04154)  (ICLR 2021)     | 22.4                      | 47.3           | NA                     | BagNet-25                          |                                                              | NA                                                      |
| [BagCert](https://arxiv.org/abs/2102.04154)  (ICLR 2021)     | 20.1                      | 47.9           | NA                     | BagNet-29                          |                                                              | NA                                                      |
| [De-randomized  Smoothing](https://arxiv.org/abs/2002.10733) (NeurIPS 2020) (from the [Smoothed  ViT](https://arxiv.org/abs/2110.07719) ) | 18.3                      | 51.5           | NA                     | ResNet-50                          | b=19; trained with pixel bands                               | [code](https://github.com/MadryLab/smoothed-vit)        |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 15.7                      | 43.6           | 44.4                   | ResNet-50 (de-randmoized  smoothed |                                                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 14.4                      | 53.7           | 56.5                   | BagNet-17                          |                                                              | [code](https://github.com/inspire-group/PatchGuard)     |
| [De-randomized  Smoothing](https://arxiv.org/abs/2002.10733) (NeurIPS 2020) | 14                        | 44.4           | NA                     | ResNet-50                          | b=25; trained with pixel bands                               | [code](https://github.com/alevine0/patchSmoothing)      |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 13.3                      | 54.4           | 58.8                   | BagNet-17                          |                                                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 9.4                       | 62.7           | 63                     | BagNet-33                          |                                                              | [code](https://github.com/inspire-group/PatchGuard)     |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 7.1                       | 49.5           | 58.8                   | BagNet-17                          |                                                              | [code](https://github.com/inspire-group/PatchGuard)     |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 6.9                       | 61.2           | 66.6                   | BagNet-33                          |                                                              | [code](https://github.com/inspire-group/PatchCleanser)  |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 1.9                       | 60.3           | 66.6                   | BagNet-33                          |                                                              | [code](https://github.com/inspire-group/PatchGuard)     |
| [IBP](https://arxiv.org/abs/2003.06693)  (ICLR 2020)         | 0                         | 0              | 0                      | NA                                 | not scale to high-resolution images                          | [code](https://github.com/Ping-C/certifiedpatchdefense) |

[(go back to table of contents)](#table-of-contents)



## Attack Detection

The attack detection defense allows the defense to alert and abstain from making predictions when it detects an attack.

#### Note 1:

1. Attack detection defenses usually can tune the defense parameters to balance the trade-off between clean accuracy and robust accuracy. 
2. Here, I only report three representative points for each defense setup (different confidence threshold tau)
   - *low-tau*: high robust accuracy and low clean accuracy; clean accuracy and robust accuracy are the same
   - high-tau: low robust accuracy and high clean accuracy; clean accuracy is close to vanilla undefended clean accuracy
   - *mid-tau*: in between
3. You are encouraged to play with the code yourself :)

#### Note 2:

1. The original [Minority Reports](https://arxiv.org/abs/2004.13799) paper does not discuss high-resolution images like ImageNet.
2. The results here (Minority Reports + PatchCleanser) are from the discussion section of the PatchCleanser paper.
3. the idea is to plug PatchCleanser's mask generation approach into the MR defense design
   https://github.com/inspire-group/PatchCleanser/blob/main/misc/pc_mr.py

### ImageNet

|                                                              | certified robust accuracy | clean accuracy | vanilla clean accuracy (if  applicable) | backbone  | comment                                                      | code                                                   |
| ------------------------------------------------------------ | ------------------------- | -------------- | --------------------------------------- | --------- | ------------------------------------------------------------ | ------------------------------------------------------ |
| [ViP](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7173_ECCV_2022_paper.php) (ECCV 2022) | 74.6                      | 74.6           | 83.7                                    | ViT-B (MAE)    | **Highest certified robust accuracy**; trained with [MAE](https://arxiv.org/abs/2111.06377); low-tau  | [code](https://github.com/UCSC-VLAA/vit_cert) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 74.3                      | 74.3           | 84.8                                    | ViT-B     | k=6; low-tau; trained with  masked images | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 73.7                      | 73.7           | 84.8                                    | ViT-B     | k=5; low-tau; trained with masked images                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 73.2                      | 73.2           | 84.8                                    | ViT-B     | k=4; low-tau; trained with masked images                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 72.8                      | 72.8           | 84.5                                    | ViT-B     | k=6; low-tau                                                 | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 71.2                      | 71.2           | 84.8                                    | ViT-B     | k=3; low-tau; trained with masked images                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 68.3                      | 68.3           | 82.3                                    | ResNet-50 | low-tau; trained with masked images                          | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 67.6                      | 67.6           | 80.8                                    | ResMLP-S  | low-tau                                                      | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 67.5                      | 67.5           | 80.2                                    | ResMLP-S  | low-tau; trained with masked images                          | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 66.6                      | 81.8           | 84.8                                    | ViT-B     | k=6; mid-tau; trained with masked images                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 65.3                      | 81.5           | 84.8                                    | ViT-B     | k=5; mid-tau; trained with masked images                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 64.5                      | 81.4           | 84.8                                    | ViT-B     | k=4; mid-tau; trained with masked images                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 64.4                      | 81.4           | 84.5                                    | ViT-B     | k=6; mid-tau                                                 | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 63.4                      | 63.4           | 82.8                                    | ResNet-50 | low-tau                                                      | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 62.1                      | 75             | 80.8                                    | ResMLP-S  | mid-tau                                                      | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 62.1                      | 81             | 84.8                                    | ViT-B     | k=3; mid-tau; trained with masked images                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 60.8                      | 75.4           | 80.2                                    | ResMLP-S  | mid-tau; trained with masked images                          | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 59.9                      | 77.8           | 82.3                                    | ResNet-50 | mid-tau; trained with masked images                          | [code](https://github.com/inspire-group/PatchCleanser) |
| [ScaleCert](https://arxiv.org/abs/2110.14120)  (NeurIPS 2021) | 55.4                      | 58.5           | 73                                      | ResNet-50 |                                                              | NA                                                     |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 51                        | 78.2           | 82.8                                    | ResNet-50 | mid-tau                                                      | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 49.8                      | 49.8           | 63                                      | BagNet-33 | low-tau; trained with masked features                        | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 48.4                      | 48.4           | 66.6                                    | BagNet-33 | low-tau                                                      | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 46.6                      | 46.6           | 56.5                                    | BagNet-17 | low-tau; trained with masked features                        | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 46.4                      | 80.3           | 80.8                                    | ResMLP-S  | high-tau                                                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 45.5                      | 45.5           | 58.8                                    | BagNet-17 | low-tau                                                      | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 39.9                      | 60.1           | 66.6                                    | BagNet-33 | mid-tau                                                      | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 39                        | 60.9           | 63                                      | BagNet-33 | mid-tau; trained with masked features                        | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 37.6                      | 84.4           | 84.5                                    | ViT-B     | k=6; high-tau                                                | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 36.4                      | 55.2           | 58.8                                    | BagNet-17 | mid-tau                                                      | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 34.7                      | 55.4           | 56.5                                    | BagNet-17 | mid-tau; trained with masked features                        | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 32.7                      | 82.3           | 82.8                                    | ResNet-50 | high-tau                                                     | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 32.4                      | 84.7           | 84.8                                    | ViT-B     | k=6; high-tau; trained with masked images                    | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 31.7                      | 84.7           | 84.8                                    | ViT-B     | k=5; high-tau; trained with masked images                    | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 30.9                      | 84.7           | 84.8                                    | ViT-B     | k=4; high-tau; trained with masked images                    | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 29.2                      | 82.1           | 82.3                                    | ResNet-50 | high-tau; trained with masked images                         | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 29.1                      | 84.6           | 84.8                                    | ViT-B     | k=3; high-tau; trained with masked images                    | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 28                        | 62.9           | 63                                      | BagNet-33 | high-tau; trained with masked features                       | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 27.6                      | 56.4           | 56.5                                    | BagNet-17 | high-tau; trained with masked features                       | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 26.7                      | 80.1           | 80.2                                    | ResMLP-S  | high-tau; trained with masked images                         | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 22.7                      | 66.3           | 66.6                                    | BagNet-33 | high-tau                                                     | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 19.9                      | 58.7           | 58.8                                    | BagNet-17 | high-tau                                                     | [code](https://github.com/inspire-group/PatchGuard)    |

[(go back to table of contents)](#table-of-contents)
