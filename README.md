# AgriFlyTwin — Moringa Leaf Classification

A machine learning experiment that classifies close-up Moringa
leaf images using colour and texture features and a Decision Tree.

Developed by **Amirah Al-baqami**, inspired by the plant-monitoring
goals of AgriFlyTwin.

## Leaf Categories

| Category | Original images |
|---|---:|
| Bacterial Leaf Spot | 857 |
| Cercospora Leaf Spot | 568 |
| Healthy | 597 |
| Yellow | 795 |
| **Total** | **2,817** |

Yellowing is a visible symptom, not a diagnosis of a specific cause.

## Method

1. Inspect the dataset and preview sample images.
2. Check for exactly duplicated image content.
3. Split the images into 80% training and 20% testing,
   preserving class proportions.
4. Resize images to 128 × 128 pixels.
5. Extract seven features: HSV channel means, HSV channel
   standard deviations, and grayscale Laplacian variance.
6. Train a Decision Tree with a maximum depth of 5
   and a minimum of 10 samples per leaf.
7. Evaluate predictions using accuracy, precision, recall,
   F1-score, and a confusion matrix.

## Results

| Metric | Result |
|---|---:|
| Training images | 2,253 |
| Testing images | 564 |
| Training accuracy | 73.55% |
| Testing accuracy | 70.92% |
| Macro F1-score | 0.71 |

These results describe one stratified image-level split.
The notebook includes saved results, a tree visualization,
and example predictions.

## How to Run

1. Download the original images from the dataset source below.
2. Upload them as a Kaggle dataset.
3. Import `AgriFlyTwin_Moringa_DecisionTree.ipynb`
   into Kaggle and attach the dataset as input.
4. Ensure the input contains an `Original Image` folder
   with the four category subfolders.
5. Run the notebook from top to bottom.

Required libraries: NumPy, pandas, Pillow, Matplotlib,
OpenCV, and scikit-learn.

Image hashing and feature extraction may take several minutes.

## Dataset and Attribution

**MoringaLeafNet, Version 5**

Khan, A., Preanto, S. A., Paul, T., and Bijoy, M. H. I. (2025).
MoringaLeafNet: A Multi-Class Leaf Disease Dataset for Precision
Agriculture and Deep Learning Research. Mendeley Data, V5.

- Source: https://data.mendeley.com/datasets/w8sr775pjb/5
- DOI: 10.17632/w8sr775pjb.5
- Dataset license: CC BY 4.0

The dataset was created by its original contributors.
This repository contains analysis code and example images
embedded in the notebook outputs. The full dataset is not included.
Images are resized for feature extraction.

## Limitations

- Features are extracted from the whole image, so background
  and lighting can influence predictions.
- Exact duplicate checking does not rule out similar images
  or multiple photographs of the same leaf.
- Performance on independent farms, drone imagery, other
  diseases, and insect pests has not been established.
- This is an experimental classifier, not a confirmed
  agricultural diagnosis or treatment tool.
