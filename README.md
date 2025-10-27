# mini-project-F8
This is repo of F8. 

Steps to execute it

Step 1: Data Collection

Set up your camera module or use a mobile camera to capture periodic images of the plant at fixed time intervals (e.g., every 1 hour or once per day).

Store all the images in a dedicated folder (e.g., plant_images/) for further processing.

Ensure the images are clear and taken from the same angle and distance for consistency.

Step 2: Preprocessing of Images

Import necessary libraries such as cv2, numpy, os, and matplotlib.

Load all the plant images from the dataset folder using OpenCV (cv2.imread).

Resize the images to a fixed dimension (e.g., 128×128 pixels) for uniform input size.

Apply basic preprocessing:

Convert images from BGR to RGB.

Normalize pixel values between 0 and 1.

Apply filters or morphological operations to reduce background noise.

Step 3: Segmentation Using U-Net Model

Define a U-Net model architecture using TensorFlow/Keras.

Create encoder and decoder blocks with convolution, batch normalization, and ReLU activation layers.

Use skip connections to retain spatial details.

Compile the model using an optimizer (e.g., Adam) and a suitable loss function (e.g., binary cross-entropy).

Train the U-Net model on the prepared dataset until satisfactory segmentation results are obtained.

After training, save the model (e.g., unet_model.h5) for future predictions.

Step 4: Plant Segmentation and Mask Generation

Load the trained U-Net model and apply it to each test image.

The model outputs a segmentation mask highlighting the plant region.

Convert the predicted mask into a binary image (thresholding).

Overlay the mask on the original image to visualize the healthy and unhealthy regions.

Step 5: Health and Stress Detection

Extract features such as the greenness level and leaf area from the segmented image.

Analyze pixel intensity or color index (like NDVI approximation using RGB values).

If the green ratio decreases significantly across timelapse frames, the plant is marked as “Unhealthy” or “Stressed.”

Otherwise, label it as “Healthy.”

Step 6: Timelapse Video Generation

Read all processed (segmented) frames in sequence using imageio or cv2.

Combine them into a GIF or MP4 timelapse video using imageio.mimsave() or cv2.VideoWriter().

The output timelapse shows the growth and health variation of the plant over time.

Example filename: timelapse.gif or plant_growth.mp4.

Step 7: Output Visualization

Display the final outputs:

Original plant image.

Segmented mask.

Overlayed image (plant health visualization).

Generated timelapse video.

Optionally, use Matplotlib to plot graphs showing:

Health index vs. time.

Area of green pixels over the growth period.

Step 8: Result and Analysis

Observe the gradual growth or stress patterns from the timelapse.

Compare multiple plants or environmental conditions (e.g., sunlight, water level).

Generate conclusions on plant health trends and stress detection efficiency.

Step 9: Storage and Cleanup

Save all results in an output folder (results/).

Delete temporary files or unused cache to free up storage space.

Export final results for report or presentation.

✅ Final Outcome:
The AgriLapse system successfully generates a timelapse video showing plant growth over time and detects plant health/stress levels using deep learning-based segmentation and image analysis.
