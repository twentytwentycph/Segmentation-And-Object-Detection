# Segmenting Lung X-ray Images with the Segment Anything Model (SAM)

## Project Overview
This project is part of the Advanced Deep Learning (ADL) course at the University of Copenhagen.
In this project, we explore the application of Metas Segment Anything Model (SAM) to medical imaging, specifically for lung segmentation in X-ray images. We investigate SAMs performance on a dataset of lung X-rays and compare various prompting methods, including manual point selection, bounding boxes derived from ground truth, and dynamically predicted bounding boxes using a custom-trained object detection model.

## Key Features
1. Implementation of SAM for lung segmentation in X-ray images
2. Comparison of different prompting methods:
   - Manual point selection
   - Ground truth-derived bounding boxes
   - Dynamically predicted bounding boxes using YOLOv8
3. Evaluation using F1 score metrics
4. Object detection model YOLOv8 for generating bounding box prompts

## Dataset
The project uses a lung X-ray dataset with corresponding segmentation masks. The dataset includes:
- 112 training images
- 12 validation images
- 123 test images

## Methodology
1. Data Preprocessing: Normalize and prepare X-ray images and segmentation masks for SAM and YOLOv8.
2. SAM Implementation: Utilize SAM with various prompting methods for lung segmentation.
3. YOLOv8 Training: Develop and train a custom object detection model to generate bounding box prompts.
4. Evaluation: Assess segmentation quality using F1 scores for different prompting methods.

## Results
We compared three different prompting methods:

1. Manual point selection method:
   - Mean F1 score: 0.7683
   - Standard deviation: 0.1357

2. Ground truth-derived bounding boxes with additional point inputs:
   - Mean F1 score: 0.9023
   - Standard deviation: 0.0471

3. YOLOv8 predicted bounding boxes:
   - Mean F1 score: 0.9200
   - Standard deviation: 0.0451

The YOLOv8 + SAM approach showed the best performance, with the highest mean F1 score and lowest standard deviation. This method also achieved a mean IoU of 0.9526 on the test set for lung localization.

## Requirements
- Python 3.x
- PyTorch
- segment-anything
- ultralytics (YOLOv8)
- OpenCV
- Matplotlib
- torchmetrics
- tqdm

## Usage
(Include brief instructions on how to run your code, e.g., main scripts to execute)
This is a simple jupyter notebook, so simply set your path and make sure your depedencies are installed from the requriements.txt. 

## Future Work
- Generally make the project more semantic and nicer code. 
- Explore more advanced prompting techniques for SAM
- Investigate the performance of SAM on other medical imaging tasks
- Optimize the YOLOv8 model further for lung detection

## Acknowledgements
- Meta AI for the Segment Anything Model
- Ultralytics for YOLOv8
- The creators of the lung X-ray dataset used in this project

## Credit
Emil Roer Thorlund | emilthorlund@gmail.dk
