# chessboard-blocks-detector


This project provides a comprehensive solution for processing images of chessboards, including perspective correction, contrast enhancement, and square classification. Designed for use in Google Colab, it allows users to analyze and visualize chessboard images efficiently.

## Overview

The algorithm processes chessboard images through several key steps, which are outlined in the flowchart below:

### Algorithm Flowchart

Here's a textual representation of the flowchart:

```
[Start]
    |
    v
[Upload Images]
    |
    v
[Perspective Correction]
    |
    v
[Image Preprocessing]
    |
    v
[Chessboard Square Detection]
    |
    v
[Display Results]
    |
    v
[End]
```

#### Flowchart Description

1. **Start**: The process begins by initializing the environment and preparing to upload images.
   
2. **Upload Images**: Users upload chessboard images via the Google Colab interface using `files.upload()`. These images are read into the environment using OpenCV.

3. **Perspective Correction**:
   - **Detect Quadrilateral**: Identify the largest quadrilateral in the image with `cv2.findContours()`.
   - **Order Points**: Use `arrange_points()` to ensure consistent point ordering.
   - **Apply Transformation**: Perform perspective correction using `cv2.getPerspectiveTransform()` and `cv2.warpPerspective()` to get a top-down view.

4. **Image Preprocessing**:
   - **Convert to Grayscale**: Simplifies the image for further processing.
   - **Enhance Contrast**: Apply CLAHE to improve image contrast.
   - **Adaptive Thresholding**: Highlight chessboard patterns for easy detection.

5. **Chessboard Square Detection**:
   - **Grid Division**: Divide the image into an 8x8 grid.
   - **Classify Squares**: Calculate pixel intensity to classify each square as 'Black' or 'White'.
   - **Annotate Image**: Use `cv2.putText()` to label squares and maintain a count of black and white squares.

6. **Display Results**: Use `matplotlib` to visualize the original and processed images, including the labeled chessboard.

7. **End**: The process concludes after displaying the results, allowing users to verify the accuracy of each step.

### Creating and Including a Flowchart

To create a flowchart for inclusion in your README:

1. **Create the Flowchart**: Use a tool like Lucidchart, draw.io, or Microsoft Visio to create a flowchart based on the description above.

2. **Export the Flowchart**: Once the flowchart is created, export it as an image (PNG or JPEG).

3. **Include in README**: Add the image to your project directory and reference it in the README using Markdown:
   ```markdown
   ![Algorithm Flowchart](path/to/your/flowchart.png)
   ```

## Detailed Steps

The flowchart provides an overview of the algorithm's workflow. Each step is crucial for accurately processing the chessboard images and achieving reliable results.

## Usage Instructions

1. **Setup**: Install dependencies using:
   ```bash
   !pip install opencv-python numpy matplotlib
   ```

2. **Execution**: Follow the steps in the Colab notebook, uploading images and running each cell in sequence.

3. **Visualization**: The final output includes original and processed images for comparison and analysis.

