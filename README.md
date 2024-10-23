Project Title: Autonomous Driving Image Segmentation with U-Net
Objective:
This project performs image segmentation for autonomous driving by using the U-Net architecture. The goal is to train the model to predict segmentation masks that identify different parts of an image, such as roads, vehicles, and pedestrians.

Workflow:
1. Dataset Preparation
The dataset is divided into RGB input images and their corresponding segmentation masks.
Segmentation Masks: These are 2D images where each pixel represents a class (e.g., road, vehicle, pedestrian).
The dataset is split into 80% for training and 20% for validation using a random selection process to ensure balanced training.
2. Data Transformation
The 2D segmentation masks are transformed into 3D arrays (one-hot encoding), where each channel corresponds to a different class label. This allows the model to output a multi-class prediction for each pixel.
Input images are resized and normalized to match the input dimensions required by the U-Net architecture.
3. U-Net Model Architecture
A U-Net architecture is used, which is particularly effective for image segmentation tasks. It consists of:
Encoder (Contraction Path): Extracts feature representations from the input images using convolutional layers and downsampling (pooling).
Decoder (Expansion Path): Upsamples the feature maps to reconstruct the original image size, outputting a pixel-level prediction.
Skip connections between corresponding layers in the encoder and decoder help the model retain spatial information.
4. Training Process
The model is trained to map each pixel in the input image to a corresponding class label in the mask using a categorical cross-entropy loss function.
The training is done with batch processing, and checkpoints are used to save the best-performing model based on validation performance.
5. Segmentation Output
After training, the U-Net model predicts a segmentation mask for each input image.
The predicted mask is a 3D array where each pixel corresponds to a specific class (e.g., road, car, pedestrian).
The performance is evaluated using metrics like accuracy and Intersection over Union (IoU), comparing the predicted masks to the ground truth.
