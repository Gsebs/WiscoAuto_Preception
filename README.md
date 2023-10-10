# WiscoAuto_Preception

CODE IMPLEMENTATION:

The provided code is an implementation of an image-processing task using the OpenCV library in Python. The task involves loading an input image, splitting it into two halves, detecting and outlining regions in the image that represent the color of traffic cones (in this case, red-orange cones), and then drawing lines connecting the centroids of these detected regions.

Here's how the code functions:

Image Preprocessing: The code loads an input image using OpenCV's cv2.imread function and then splits it into two equal halves using NumPy slicing. This split is done to process each half independently, making the code more modular.

Cone Detection and Line Drawing: The find_cones_and_draw_lines function is defined to handle cone detection and line drawing. It first converts the image from the BGR color space to the HSV color space, as HSV is better suited for detecting specific colors. It then creates a mask to isolate regions of the image that match the specified red-orange color range. Contours of detected regions in the mask are found, and centroids are calculated for these regions. If a centroid is located in the upper fourth of the image's height (presumably where traffic cones would be), it is considered valid. Lines are drawn connecting these centroids on the image.

Merging and Displaying: The find_cones_and_draw_lines function is applied to both halves of the image. After processing, the two halves are merged horizontally using NumPy's np.hstack to create the final output image. The merged image is then displayed using cv2_imshow.

Saving the Result: Additionally, the code saves the merged image as a PNG file and waits for a key press before closing the display windows.

In summary, this code demonstrates how to perform color-based object detection and visualization on an image, specifically targeting the detection and visualization of red-orange traffic cones. It showcases the capabilities of OpenCV for image processing tasks, such as contour detection and drawing, color space conversion, and image manipulation.


THE PROCESS IN CREATING THE FUNCTION:


During the process of creating the function for cone detection and visualization, several approaches and implementations were tried, each building upon the previous one. The initial implementation successfully loaded the image, split it into halves, and converted it to the HSV color space. However, challenges arose when defining the precise color range for red-orange traffic cones. Experimentation with various HSV color ranges was needed to accurately isolate cone regions. The implementation also involved contour detection, centroid calculation, and line drawing, which worked effectively for highlighting detected cones. Additionally, splitting and merging the image helped process each half independently, contributing to better modularity and organization of the code. However, the code might benefit from more robust methods for detecting cones in varying lighting conditions or when cones are partially obscured.

Overall, the iterative process of refining the color range and fine-tuning the cone detection parameters played a crucial role in making the function effective. While the code was able to detect and visualize traffic cones in a controlled environment, it may require further adjustments to handle real-world scenarios with varying lighting conditions and occlusions.
