

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
9. [Validating and Testing](#validating-and-testing)
10. [Results](#results)

## Project Setup

First, clone the required repository and install necessary libraries. This involves using Git to clone the `GradientGenerator` repository and installing Python packages like `ultralytics`, `gdown`, `Augmentor`, and `tqdm`.

## Directory Structure

Create the necessary directories for storing background images, training data, validation data, and test data.

## Downloading Data

Download the required project data, including input images, background images, and test images from Google Drive. This ensures you have all the necessary resources for the project.

## Background Generation

1. **Creating Gradient Backgrounds**

   Initially, gradient background images are generated using the `create_back(r_channel, g_channel, b_channel)` function. This function utilizes predefined color channels (`r_channel, g_channel, b_channel`) and fixed colors such as white, black, yellow, red, and blue to produce gradient background images sized at 640x640 pixels. For each predefined color, a gradient background image is created, and its name and path are updated accordingly.
   
   Sample images:
   
   [![Uploading image.png…]()]

2. **Incorporating Downloaded Background Images**

   In this stage, alongside gradient color backgrounds, 10 challenging images are used as additional backgrounds. These images are downloaded from other sources and moved to the `backgrounds_images` folder.

   View images:
   
   [Add link or describe how to view the images]

3. **Applying Random Transformations to Input Images**

   Using the Augmentor library, random transformations are applied to input images to increase dataset diversity. These transformations include rotation, horizontal and vertical flips, contrast and brightness adjustments, zooming, distortion, and random cropping.

   First, a pipeline is created to apply these random transformations to input images. Then, different transformations are added to the pipeline with specified probabilities:
   - `rotate`: Random rotation with a defined probability and maximum rotation angle.
   - `flip_left_right`: Horizontal flipping with a defined probability.
   - `flip_top_bottom`: Vertical flipping with a defined probability.
   - `random_contrast`: Random contrast adjustment with a defined probability and range.
   - `random_brightness`: Random brightness adjustment with a defined probability and range.
   - `zoom_random`: Random zoom with a defined probability and area percentage.
   - `random_distortion`: Random distortion with a defined probability and grid size.
   - `shear`: Random shearing with a defined probability and maximum shear angle.

   Finally, a specified number of images (here, 50 images) are generated with these random transformations applied.

   [Add any additional details or clarifications necessary]

   
## Generating Backgrounds

Generate background images using the `GradientGenerator` script. This step involves creating various gradient backgrounds that will be used later to create composite images.

## Image Augmentation

Apply various transformations to enhance the diversity of input images. The Augmentor library is used to perform these transformations, which helps in increasing the variety and robustness of the dataset.

## Creating Composite Images

Combine input images with different backgrounds to create composite images. Additionally, generate corresponding labels that will be used for training the YOLO model. This step is crucial for creating a comprehensive dataset that the model can learn from.

## Preparing the Dataset

Split the dataset into training, validation, and test sets. Typically, 70% of the data is used for training, 20% for validation, and 10% for testing. This ensures that the model can be properly evaluated on unseen data.

## Training YOLOv8

Train the YOLOv8 model on the custom dataset. This involves specifying various training parameters such as the number of epochs, image size, and augmentation settings to fine-tune the model.

## Validating and Testing

Validate the trained model on the validation dataset and make predictions on the test dataset. This step helps in assessing the performance of the model and ensuring that it generalizes well to new data.

## Results

Display the results of predictions on test images. This involves visualizing the model's predictions to qualitatively assess its performance and identify areas for improvement.

## Acknowledgements

- [GradientGenerator Repository](https://github.com/HYOUG/GradientGenerator)
- [YOLOv8 by Ultralytics](https://github.com/ultralytics/ultralytics)

---

Feel free to customize this README file further according to your project's specific needs and details.
