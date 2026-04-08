# README - CPSC 542 Assignment 2

---

## Project Information

| Field | Details |
| :---- | :---- |
| **Project** | Instacart image-based reorder prediction checkpoint  |
| **Primary code repository** | [GitHub repo](https://github.com/ehrmanj-chap/cpsc_assignment_one)  |
| **Instacart dataset** | [Kaggle dataset link](https://www.kaggle.com/datasets/yasserh/instacart-online-grocery-basket-analysis-dataset)  |
| **Product image source** | [Open Food Facts](https://world.openfoodfacts.org/)  |
| **Task type** | Binary classification of high-reorder vs. low-reorder products from product images  |

---

## Group Members

| Name | Role / Notes |
| :---- | :---- |
| **Jordan Ehrman** | Lead assembly of the writeup and broader project framing; repository owner reflected in the provided GitHub link.  |
| **Colton Wedell** | Implemented the core notebook experiments, model training runs, and image-loading pipeline used in the checkpoint.  |
| **Amelia Hammer** | Provided conceptual support and identified Open Food Facts as a practical external image source for the checkpoint.  |

---

## Data Access Instructions

* The Instacart tabular data used for this checkpoint comes from the public Kaggle dataset linked above.

* The image side of the checkpoint uses Open Food Facts as an external image source.

* The current workflow first computes product-level reorder statistics from Instacart purchase history, then labels the top quartile as high-reorder and the bottom quartile as low-reorder, excluding the middle 50 percent.

* Product names are then used to query Open Food Facts, and candidate matches are ranked by string similarity before selecting the top acceptable image.

* Because the checkpoint code uses external image URLs rather than bundling all image files directly into the repository, internet access may be required at runtime for image retrieval unless the matched image set is cached locally in advance.

---

## Implementation Note on Augmentation

* The project proposal describes light training-time augmentation such as flips, slight rotations, and mild brightness or contrast jitter.

* However, the uploaded training notebook currently uses resizing, tensor conversion, and normalization only.

* The README therefore describes augmentation as a planned extension to the baseline preprocessing pipeline rather than as something fully implemented in the present checkpoint notebook.

---

## Resources Used

* **PyTorch and torchvision** for model construction and training.

* **Pillow** for image loading and RGB conversion.

* **scikit-learn** for dataset splitting and evaluation metrics.

* **Instacart Market Basket Analysis dataset** on Kaggle.

* **Open Food Facts** website / API / image infrastructure.

* **GitHub repository** for code submission and versioning.
