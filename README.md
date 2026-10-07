# Pap-Smear Cell Classification — 1st place 🥇

> Télécom Paris · IMA205 *Learning for images & object recognition* · Kaggle class challenge 2021
> **Saifeddine Barkia**, ranked **1st out of 48 students**

Classify cervical cells from Pap-smear microscopy images, both as a binary task (normal vs abnormal) and as a multi-class task (cell type). Automated screening matters: the WHO estimates over 500,000 new cervical cancer cases a year, around 90% of them preventable with early detection, and manual slide reading is slow and error-prone.

**Leaderboard result: MCC 0.832** (Matthews correlation coefficient) · [Competition page](https://www.kaggle.com/c/ima205challenge2021bis/overview)

## Approach

1. **Data:** each cell comes with its image plus nucleus and cytoplasm segmentation masks, used to build 3 views per cell.
2. **Classical ML baseline:** hand-crafted features (HOG descriptors, colour histograms, Haralick texture and Zernike moments) computed on the cell, nucleus and cytoplasm images with SVM, AdaBoost and Random Forest, tuned by grid search.
3. **Deep learning:** transfer learning with ImageNet-pretrained CNNs, data augmentation and an MCC-based validation metric. This gave the best leaderboard score.

The notebook [`Binary & multi classification.ipynb`](./Binary%20%26%20multi%20classification.ipynb) contains the full pipeline. It needs about 25 GB of RAM; see the notes inside.

**Stack:** Python · TensorFlow/Keras · scikit-learn · scikit-image · mahotas · OpenCV
