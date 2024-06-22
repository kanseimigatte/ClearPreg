# ClearPreg Model Documentation

ClearPreg is a model designed to predict pregnancy test results from images. There are three models, each built on a ResNet architecture with an additional layer. All model architectures are designed for binary image classification tasks. The required data was scraped from "countdowntopregnancy.com," and a total of 1200 images were used to train the model.

## Code Explanation

### Image Search

The image search code primarily uses the Selenium library, incorporating basic HTML and JavaScript logic. The number of pages to be scraped can be adjusted as needed. Ensure you use Chrome WebDriver version 125 or later.

### Model Training

#### ClearPreg_10_256, ClearPreg_23_350, ClearPreg_40_350

These scripts train the models with different hyperparameters using TensorFlow. All models were trained on an A100 GPU, except for ClearPreg_23_350, which was trained on an L4 GPU. The training process generally takes about 20 minutes.

### Data Augmentation

The data augmentation code serves two purposes:
1. Preprocessing the scraped images (grayscaling, rotating, resizing).
2. Preprocessing test images (user images) by grayscaling and resizing them.

### Model Evaluation

The ClearPregModelEval code is used to load the trained models and test them on a test dataset. Preprocessed test images are processed again in this code to ensure a better flow.
