## Project Overview
We explore the application of Meta's Segment Anything Model (SAM) to medical imaging, specifically for lung segmentation in X-ray images. We investigate SAM's performance on a dataset of lung X-rays and compare various prompting methods, including manual point selection, bounding boxes derived from ground truth, and dynamically predicted bounding boxes using a custom-trained object detection model (YOLOv8).

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
3. YOLOv8 Training: Train a custom object detection model to generate bounding box prompts.
4. Evaluation: Observe segmentation quality using F1 scores for different prompting methods.

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
This project is implemented as a Jupyter notebook and was developed and run using Google Colab for GPU support. It is highly recommended to use a similar environment with GPU acceleration if you want to run the code yourself.

To run the project:

1. Ensure you have all the dependencies installed. You can install them using:
- pip install -r requirements.txt

2. If using Google Colab (recommended):
- Upload the notebook to Google Colab
- Enable GPU acceleration in the runtime settings
- Mount your Google Drive if you're storing the dataset there

3. If running locally:
- Make sure you have Jupyter Notebook or JupyterLab installed
- Ensure you have access to a GPU and the necessary CUDA libraries

4. Set your working directory to the project folder

5. Open the Jupyter notebook and run the cells sequentially

Note: Due to the computational intensity of the SAM model and YOLOv8 training, running this on a machine without GPU support may be extremely time consuming.
   
## Future own Work
- Generally make the project more semantic and improve code for better readability and maintainability. 
- Explore more advanced prompting techniques for SAM
- Potentially investigate the performance of SAM on other medical imaging tasks
- Optimize the YOLOv8 model further for lung detection

## Acknowledgements
- Meta AI for the Segment Anything Model
- Ultralytics for YOLOv8
- The creators of the lung X-ray dataset used in this project:
     Bram van Ginneken, Mikkel B. Stegmann, Marco Loog. [Segmentation of anatomical structures in chest radiographs using supervised methods: a      comparative study on a public database](https://doi.org/10.1016/j.media.2005.02.002). *Medical Image Analysis* 10(1): 19-40, 2006


