# Template Matching 
 Object Detection Project Using Limited Images

This project aims to detect objects in images using a very limited amount of input data. I have started this project with four different images of mice with varying colors and patterns. One of the features of this project is the use of diverse and varied inputs, which enhances the diversity of the training dataset and improves the model's accuracy.

In this project, I have used ten different images as backgrounds. These backgrounds are combined with various input images to create a comprehensive and diverse dataset for training the YOLOv8 model. To achieve this, several libraries and tools for image processing, data augmentation, and model training have been utilized.

This project allows me to create a rich and diverse training dataset with minimal input data.

## Table of Contents
1. [Project Setup](#project-setup)
2. [Directory Structure](#directory-structure)
3. [Downloading Data](#downloading-data)
4. [Generating Backgrounds](#generating-backgrounds)
5. [Image Augmentation](#image-augmentation)
6. [Creating Composite Images](#creating-composite-images)
7. [Preparing the Dataset](#preparing-the-dataset)
8. [Training YOLOv8](#training-yolov8)
9. [Model Evaluation](#model-evaluation)
10. [Model Inference](#model-inference)
11. [Results and Applications](#results-and-applications)
12. [Requirements](#Requirements)
13. [Contribution](#Contribution)
14. [Acknowledgements](#acknowledgements)
15. [Contact](#Contact)
16. [References](#References)



## Project Setup
First, clone the required repository and install necessary libraries. This involves using Git to clone the `GradientGenerator` repository and installing Python packages like `ultralytics`, `gdown`, `Augmentor`, and `tqdm`.

## Directory Structure
Create the necessary directories for storing background images, training data, validation data, and test data.

## Downloading Data
Download the required project data, including input images, background images, and test images from Google Drive. This ensures you have all the necessary resources for the project.

## Generating Backgrounds
1. **Creating Gradient Backgrounds**
   Initially, gradient background images are generated using the `create_back(r_channel, g_channel, b_channel)` function. This function utilizes predefined color channels (`r_channel, g_channel, b_channel`) and fixed colors such as white, black, yellow, red, and blue to produce gradient background images sized at 640x640 pixels. For each predefined color, a gradient background image is created, and its name and path are updated accordingly.

2. **Incorporating Downloaded Background Images**
   In this stage, alongside gradient color backgrounds, 10 challenging images are used as additional backgrounds. These images are downloaded from other sources and moved to the `backgrounds_images` folder.

## Image Augmentation
Random transformations are applied to input images to increase dataset diversity using the Augmentor library. These transformations include rotation, horizontal and vertical flips, contrast and brightness adjustments, zooming, distortion, and random cropping.

## Creating Composite Images
### Method 1:
#### Image Size 50x50 pixels
For each input image resized to 50x50 pixels, the final image is placed on each available background. This process is repeated for 15 random positions per background, resulting in 15 final images for each background.

#### Image Size 110x110 pixels
For each input image resized to 110x110 pixels, the final image is placed on each available background. This process is repeated for 10 random positions per background, resulting in 10 final images for each background.

### Method 2: Random Number of Input Images on Backgrounds
In this method, a random number of input images (between 2 to 5 images) are placed on each background. This adds variability to the dataset by allowing a different number of input images to be combined on each background.

### Overlapping Check of Images
To ensure that the input images do not overlap on the backgrounds:
- A function is utilized to check the coordinates of each image.
- If overlap is detected, the function determines a new position for the image to avoid overlap.

These methods aim to generate a diverse dataset for training the YOLO network, enhancing its ability to detect objects effectively across various backgrounds and scenarios. Each method offers a different approach to combining input images with backgrounds, contributing to the robustness and generalization of the trained model.

## Generating Labels for YOLO
For each final image, a label file in text format is generated that specifies the normalized position and size of each object in the image relative to the dimensions of the background image. Generally, this format includes: class x_center y_center width height.

## Preparing the Dataset
Split the dataset into training, validation, and test sets. 70% of the data is used for training, 20% for validation, and 10% for testing. This ensures that the model can be properly evaluated on unseen data.

## Training YOLOv8
The YOLOv8 model is trained using the training dataset for 7 epochs. This includes configuring various training parameters such as the number of epochs, image size, and settings for data augmentation to optimize the model. Data augmentation settings involve changes in color, rotation, translation, scaling, and more.

## Model Evaluation
After training, the model is evaluated using validation data to assess its performance.

## Model Inference
The trained model is used for predicting objects in new images. Prediction results are displayed, and some samples of predicted images are shown as output.

## Results and Applications
This project enables us to generate a rich and diverse training set of images using a limited number of input images, thereby improving the quality and accuracy of object detection models. The trained model can accurately detect desired objects in new images.

### Requirements
- Python 3.x
- Ultralytics
- Augmentor
- YOLO
- tqdm
- NumPy
- Pandas
- gdown
- random

### Contribution
Contributions are welcome! Please fork the repository, make your changes, and submit a pull request.

## Acknowledgements
- [GradientGenerator Repository](https://github.com/HYOUG/GradientGenerator)
- [YOLOv8 by Ultralytics](https://github.com/ultralytics/ultralytics)

### Contact
For any inquiries or support, please contact [za.shahlaie@gmail.com](mailto:za.shahlaie@gmail.com).

### References
- [Blending images using OpenCV](https://medium.com/featurepreneur/blending-images-using-opencv-bfc9ab3697b7)
- [Augmentation settings](https://docs.ultralytics.com/usage/cfg/#augmentation-settings)
- (https://rumn.medium.com/yolo-data-augmentation-explained-turbocharge-your-object-detection-model-94c33278303a)
