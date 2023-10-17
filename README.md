###### #############################
###  Shadow Remover              ###
###  Author: Sean Joseph Chow    ###
###  Version: 3.0                ###
###  Date: 10/10/2023            ###
##### ##############################

This Python project is designed to remove shadows from images and videos. It has been tested on Python 3.10 and can be run on both a local machine and Google Colab. Please follow the instructions below to set up and run the code.

### Installation

Before running the code, make sure to install the required libraries. You can do this by uncommenting the installation commands in the first cell of the Colab notebook or if you have cloned the github repository then by running the following command:

```
pip install -r requirements.txt
```

### Dataset Paths

Ensure that you have the following directory structure and provide correct paths for the dataset:

- Inside the `train` directory, there should be `train_A` (Shadow Images) and `train_C` (Non-Shadow Images) directories.
- Inside the `test` directory, there should be `test_A` (Shadow Images) and `test_C` (Non-Shadow Images) directories.
- Similarly, inside the `train_custom` directory, there should be `train_custom_A` and `train_custom_C` directories.
- Inside the `test_custom` directory, there should be `test_custom_A` and `test_custom_C` directories.

Update the following variables with the correct paths, all of these variables are in the 4th cell of the notebook:

```python
shadow_path = '/path/to/shadow_image.png' # Path to a shadow image for visualization
no_shadow_path = '/path/to/non_shadow_image.png' # Path to a non-shadow image for visualization

train_path = '/path/to/train' # Path to the training data for the first stage
test_path = '/path/to/test' # Path to the test data for the first stage

custom_train = '/path/to/train_custom' # Path to the training data for the second stage or custom data
custom_test = '/path/to/test_custom' # Path to the test data for the second stage or custom data

checkpoint_dir = '/path/to/training_checkpoints' # Path to save model weights
log_dir = '/path/to/logs/' # Path to save training logs

input_video_path = '/path/to/input_video.mp4' # Path to the input video for prediction
output_video_path = '/path/to/output_video.mp4' # Path to store the output video prediction
```

### Usage

Once you've set the correct paths, you can run the code to perform shadow removal on images and videos.

### Code


1) final_shadow_remover.ipynb  # This is the improved version of the first approch
Output: no_shadow_output_v8  # This is the test video used in sampling for evaluation metric results.

2) freeze_layer_shadow_remover  # This is the second approach that added the step of freezing most layers in the generator and discriminator for more targeted
training. However, this method did not yield enhanced outcomes.

3) frame_sample_and_metrics.ipynb # This handles the sampling of images from the output video, then outputs a table and graph for evaluation metrics. Extracted images are saved in the folder img_extract

### Videos Output

# Input (root location)
shadow_input.mp4

# Output (root location)
no_shadow_output_v8.mp4

second_step_output.mp4






