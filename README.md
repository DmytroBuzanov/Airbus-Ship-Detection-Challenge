# Airbus Ship Detection

[Airbus Ship Detection](https://www.kaggle.com/c/airbus-ship-detection) 

The goal of the competition is to analyze satellite images of container ships and produce segmentation masks of the ships.

To generate solutions, I created a two model pipeline. The first model is a ResNeXt50 based classification model that classified images as containing ships or not containing ships. The second model is a ResNet34 based U-Net model that generated segmentation masks for images classified as ships. The two model solution worked much better than training a U-net segmentation model to process all images.

The solution is broken up into several notebooks:


#### EDA.ipynb: Preparing Masks as Images
Ground truth segmentation masks are provided as run length encoded strings. This notebook turns encoded masks into images.

#### Model_based_on_U-net.ipynb: Training the Segmentation Model
This notebook shows training the segmentation model and some of the tricks used to maximize performance

#### Training_model.ipynb: Training the Classification Model
This notebook shows training the classification model

#### Prediction.ipynb: Generating a Submission
This notebook shows using the two-model approach to filter ship containing images with the classification model, then generating segmentation masks for ship containing images using the segmentation model. Predicted masks are converted into run length encoded strings for the solution.
