# Plant Leaf Disease Region Segmentation

## Digital Image Processing Mini Project

This project focuses on segmenting diseased or affected regions in plant leaf images using classical Digital Image Processing techniques.

The project compares different segmentation methods and evaluates their performance against available ground-truth masks.

## Problem Statement

Plant leaf diseases often appear as localized spots or affected regions on the leaf surface. Identifying these regions from leaf images is useful for visual disease assessment and can support automated plant-health analysis.

This project uses classical image processing techniques to identify and segment potential diseased regions.

## Objectives

- Load and inspect plant leaf images with their ground-truth disease masks.
- Preprocess images using grayscale conversion and Gaussian smoothing.
- Apply Otsu thresholding.
- Apply Adaptive Gaussian thresholding.
- Apply HSV color-based segmentation.
- Improve segmentation masks using morphological opening and closing.
- Evaluate the methods using IoU, Dice Coefficient and Pixel Accuracy.
- Compare the methods on 100 matched images.

## Dataset

**Dataset:** Plants Leaves Dataset with Masks for Segmentation

**Source:** Kaggle

**Dataset Link:**  
https://www.kaggle.com/datasets/baseto/plants-leaves-dataset-with-masks-for-segmentation

The dataset contains:

- 1611 plant leaf images
- 1611 corresponding masks
- Image size: 128 × 128 pixels
- RGB images
- Binary ground-truth masks

The complete dataset is not included in this repository.

## Methodology

The project follows these main steps:

1. Dataset extraction and image-mask matching
2. Ground-truth mask preparation
3. Grayscale conversion
4. Gaussian smoothing
5. Otsu thresholding
6. Adaptive Gaussian thresholding
7. HSV color-based segmentation
8. Morphological opening and closing
9. Evaluation using IoU, Dice and Pixel Accuracy
10. Comparison of results across 100 matched images

## Techniques Used

### Otsu Thresholding

Otsu thresholding is used as a global intensity-based segmentation method.

### Adaptive Thresholding

Adaptive Gaussian thresholding uses local neighbourhood information to calculate the threshold.

### HSV Color-Based Segmentation

HSV color space is used to identify potential yellow/brown affected regions based on their color characteristics.

### Morphological Processing

Morphological opening is used to remove small isolated noise, while closing is used to fill small holes and gaps in detected regions.

## Evaluation Metrics

The segmentation methods are evaluated using:

- Intersection over Union (IoU)
- Dice Coefficient
- Pixel Accuracy

The methods are compared against the corresponding ground-truth masks.

## Results

The methods were evaluated on 100 matched images.

| Method | Average IoU | Average Dice | Average Pixel Accuracy |
|---|---:|---:|---:|
| Adaptive Thresholding | 0.1001 | 0.1590 | 0.8176 |
| Color-Based | 0.2731 | 0.3886 | 0.9350 |
| Color-Based + Closing | 0.2900 | 0.4053 | 0.9341 |
| Color-Based + Opening | 0.2443 | 0.3481 | 0.9390 |
| Otsu Thresholding | 0.1669 | 0.2160 | 0.7542 |

Color-Based + Closing achieved the highest average IoU and Dice values in the 100-image experiment, while Color-Based + Opening achieved the highest Pixel Accuracy.

## Limitations

- Fixed HSV threshold ranges may not work equally well under different lighting conditions.
- Different plant species and disease types can have different lesion colors.
- Healthy leaf pigmentation can sometimes be similar to the selected disease-color range.
- Pixel Accuracy can be misleading when disease regions occupy only a small portion of the image.
- The experiment uses 100 images as an evaluation subset rather than the complete dataset.

## Future Scope

- Use adaptive color clustering methods such as K-Means in alternative color spaces.
- Use texture features such as GLCM or LBP.
- Explore more advanced segmentation methods.
- Evaluate the approach on a larger and more diverse image set.

## Tools and Technologies

- Python
- Google Colab
- OpenCV
- NumPy
- Pandas
- Matplotlib

## Repository Structure

```text
Plant-Leaf-Disease-Segmentation/
│
├── report/
│   └── Plant_Leaf_Disease_Segmentation_Report.pdf
│
├── screenshots/
│   └── Project output screenshots
│
├── source_code.ipynb
├── requirements.txt
└── README.md
