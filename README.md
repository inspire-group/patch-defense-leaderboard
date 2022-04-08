# Leaderboard: Certifiable Robustness against Adversarial Patch Attacks

This repository provides a leaderboard for certifiable robustness against adversarial patch attacks.

Check out [our paper list and tutorials](https://github.com/xiangchong1/adv-patch-paper-list) for adversarial patch attacks and defenses! 



## About

For now, this leaderboard focuses on the setting of

1. Image classification task
2. ImageNet dataset
3. One 2% square patch anywhere on the image
4. Robust prediction and attack detection (read this [explanation](https://github.com/xiangchong1/adv-patch-paper-list#robust-prediction-vs-attack-detection) for the difference between these two notions)

Stay tuned for future updates on different datasets and tasks :)

### Annotated attributes

We include the following properties of different defenses in this leaderboard.

1. **Defense name and publication venue**.
2. **Certified robust accuracy:** certified robust accuracy for a 2%-pixel square patch anywhere on the image. All leaderboards are sorted by certified robust accuracy
3. **Clean accuracy:** clean accuracy of the defended models
4. **Vanilla clean accuracy:** clean accuracy of vanilla undefended models (if the defense is built upon off-the-shelf models)
5. **Backbone:** the backbone used for each defense
6. **Comment:** additional comments for each defense
7. **Code:** most defenses have open-sourced implementations by the authors or others

**Note:** We discuss more properties of different defenses in [another copy of leaderboards](https://docs.google.com/spreadsheets/d/1zDBg5AmpWq92c_MaSx6vq4FsOUnzu57i8aUuex2NT7Y/edit?usp=sharing) hosted on Google Sheet.

### Contributions

If you have new results and want to contribute to the leaderboard. Please submit a pull request or email me (Chong Xiang; cxiang@princeton.edu)

## Table of Contents

- [**Robust Prediction**](#robust-prediction)
- [**Attack Detection**](#attack-detection)

## Robust Prediction

The robust prediction defense requires the defense model to always predict a robust label (without any abstention).

|                                                              | Certified robust accuracy | Clean accuracy | Vanilla clean accuracy | Backbone                           | Comment                                  | Code                                                    |
| ------------------------------------------------------------ | ------------------------- | -------------- | ---------------------- | ---------------------------------- | ---------------------------------------- | ------------------------------------------------------- |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 62.1                      | 83.9           | 84.8                   | ViT-B                              | SOTA with known patch size               | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 61.6                      | 83.8           | 84.8                   | ViT-B                              |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 59.8                      | 83.7           | 84.8                   | ViT-B                              |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 59.4                      | 83.6           | 83.7                   | ViT-B                              |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 56.1                      | 83.3           | 84.8                   | ViT-B                              |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 53.8                      | 79.4           | 80.2                   | ResMLP-S                           |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 53.1                      | 79.6           | 80.8                   | ResMLP-S                           |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 53                        | 81.6           | 82.3                   | ResNet-50                          |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 41.7                      | 75.58          | NA                     | ViT-B                              | SOTA with unknown patch size             | NA                                                      |
| [PatchCleanser](https://arxiv.org/abs/2108.09135)  (USENIX Security 2022) | 41.6                      | 81.1           | 82.8                   | ResNet-50                          |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 40.79                     | 75.3           | NA                     | ViT-B                              |                                          | NA                                                      |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 40.72                     | 73.49          | NA                     | ViT-B                              |                                          | NA                                                      |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 38.3                      | 69.3           | NA                     | ViT-B                              | SOTA with unknown patch size (with code) | [code](https://github.com/MadryLab/smoothed-vit)        |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 38.2                      | 73.2           | NA                     | ViT-B                              |                                          | [code](https://github.com/MadryLab/smoothed-vit)        |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 36.9                      | 68.3           | NA                     | ViT-B                              |                                          | [code](https://github.com/MadryLab/smoothed-vit)        |
| [Smoothed  ViT](https://arxiv.org/abs/2110.07719) (CVPR 2022) | 31.6                      | 63.5           | NA                     | ViT-S                              |                                          | [code](https://github.com/MadryLab/smoothed-vit)        |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 30.06                     | 67.14          | NA                     | ViT-S                              |                                          | NA                                                      |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 29.74                     | 69.88          | NA                     | ViT-S                              |                                          | NA                                                      |
| [ECViT](https://arxiv.org/abs/2203.08519)  (CVPR 2022)       | 28.85                     | 64.69          | NA                     | ViT-S                              |                                          | NA                                                      |
| [De-randomized  Smoothing](https://arxiv.org/abs/2002.10733) (NeurIPS 2021) (from the  [Smoothed ViT](https://arxiv.org/abs/2110.07719) ) | 28.1                      | 61.4           | NA                     | WRN-101-2                          |                                          | [code](https://github.com/MadryLab/smoothed-vit)        |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 26                        | 54.6           | 56.5                   | BagNet-17                          |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 24.1                      | 60.4           | 63                     | BagNet-33                          |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [BagCert](https://arxiv.org/abs/2102.04154)  (ICLR 2021)     | 22.7                      | 45.3           | NA                     | BagNet-17                          |                                          | NA                                                      |
| [BagCert](https://arxiv.org/abs/2102.04154)  (ICLR 2021)     | 22.4                      | 47.3           | NA                     | BagNet-25                          |                                          | NA                                                      |
| [BagCert](https://arxiv.org/abs/2102.04154)  (ICLR 2021)     | 20.1                      | 47.9           | NA                     | BagNet-29                          |                                          | NA                                                      |
| [De-randomized  Smoothing](https://arxiv.org/abs/2002.10733) (NeurIPS 2021) (from the [Smoothed  ViT](https://arxiv.org/abs/2110.07719) ) | 18.3                      | 51.5           | NA                     | ResNet-50                          |                                          | [code](https://github.com/MadryLab/smoothed-vit)        |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 15.7                      | 43.6           | 44.4                   | ResNet-50 (de-randmoized  smoothed |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 14.4                      | 53.7           | 56.5                   | BagNet-17                          |                                          | [code](https://github.com/inspire-group/PatchGuard)     |
| [De-randomized  Smoothing](https://arxiv.org/abs/2002.10733) (NeurIPS 2021) | 14                        | 44.4           | NA                     | ResNet-50                          |                                          | [code](https://github.com/alevine0/patchSmoothing)      |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 13.3                      | 54.4           | 58.8                   | BagNet-17                          |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 9.4                       | 62.7           | 63                     | BagNet-33                          |                                          | [code](https://github.com/inspire-group/PatchGuard)     |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 7.1                       | 49.5           | 58.8                   | BagNet-17                          |                                          | [code](https://github.com/inspire-group/PatchGuard)     |
| [PatchGuard](https://arxiv.org/abs/2005.10884)  (USENIX Security 2021) | 6.9                       | 61.2           | 66.6                   | BagNet-33                          |                                          | [code](https://github.com/inspire-group/PatchCleanser)  |
| [Clipped  BagNet](https://people.eecs.berkeley.edu/~daw/papers/bagnet-dls20.pdf) (DLS  2020) | 1.9                       | 60.3           | 66.6                   | BagNet-33                          |                                          | [code](https://github.com/inspire-group/PatchGuard)     |
| [IBP](https://arxiv.org/abs/2003.06693)  (ICLR 2020)         | 0                         | 0              | 0                      | NA                                 | not scale to high-resolution images      | [code](https://github.com/Ping-C/certifiedpatchdefense) |

[(go back to table of contents)](#table-of-contents)



## Attack Detection

The attack detection defense allows the defense to alert and abstain from making predictions when it detects an attack.

|                                                              | Certified robust accuracy | Clean accuracy | Vanilla clean accuracy (if  applicable) | Backbone  | Comment                           | Code                                                   |
| ------------------------------------------------------------ | ------------------------- | -------------- | --------------------------------------- | --------- | --------------------------------- | ------------------------------------------------------ |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 74.3                      | 74.3           | 84.8                                    | ViT-B     | Highest certified robust accuracy | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 73.7                      | 73.7           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 73.2                      | 73.2           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 72.8                      | 72.8           | 84.5                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 71.2                      | 71.2           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 68.3                      | 68.3           | 82.3                                    | ResNet-50 |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 67.6                      | 67.6           | 80.8                                    | ResMLP-S  |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 67.5                      | 67.5           | 80.2                                    | ResMLP-S  |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 66.6                      | 81.8           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 65.3                      | 81.5           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 64.5                      | 81.4           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 64.4                      | 81.4           | 84.5                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 63.4                      | 63.4           | 82.8                                    | ResNet-50 |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 62.1                      | 75             | 80.8                                    | ResMLP-S  |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 62.1                      | 81             | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 60.8                      | 75.4           | 80.2                                    | ResMLP-S  |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 59.9                      | 77.8           | 82.3                                    | ResNet-50 |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [ScaleCert](https://arxiv.org/abs/2110.14120)  (NeurIPS 2021) | 55.4                      | 58.5           | 73                                      | ResNet-50 |                                   | NA                                                     |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 51                        | 78.2           | 82.8                                    | ResNet-50 |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 49.8                      | 49.8           | 63                                      | BagNet-33 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 48.4                      | 48.4           | 66.6                                    | BagNet-33 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 46.6                      | 46.6           | 56.5                                    | BagNet-17 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 46.4                      | 80.3           | 80.8                                    | ResMLP-S  |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 45.5                      | 45.5           | 58.8                                    | BagNet-17 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 39.9                      | 60.1           | 66.6                                    | BagNet-33 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 39                        | 60.9           | 63                                      | BagNet-33 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 37.6                      | 84.4           | 84.5                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 36.4                      | 55.2           | 58.8                                    | BagNet-17 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 34.7                      | 55.4           | 56.5                                    | BagNet-17 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 32.7                      | 82.3           | 82.8                                    | ResNet-50 |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 32.4                      | 84.7           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 31.7                      | 84.7           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 30.9                      | 84.7           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 29.2                      | 82.1           | 82.3                                    | ResNet-50 |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 29.1                      | 84.6           | 84.8                                    | ViT-B     |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 28                        | 62.9           | 63                                      | BagNet-33 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 27.6                      | 56.4           | 56.5                                    | BagNet-17 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [Minority  Reports](https://arxiv.org/abs/2004.13799) (ACNS Workshop 2020) +  [PatchCleanser](https://arxiv.org/abs/2108.09135) (USENIX Security 20222) | 26.7                      | 80.1           | 80.2                                    | ResMLP-S  |                                   | [code](https://github.com/inspire-group/PatchCleanser) |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 22.7                      | 66.3           | 66.6                                    | BagNet-33 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |
| [PatchGuard++](https://arxiv.org/abs/2104.12609)  (ICLR Workshop 2021) | 19.9                      | 58.7           | 58.8                                    | BagNet-17 |                                   | [code](https://github.com/inspire-group/PatchGuard)    |

[(go back to table of contents)](#table-of-contents)
