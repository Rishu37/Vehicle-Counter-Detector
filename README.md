Vehicle Detection and Counting System
This project involves developing a vehicle detection and counting system using OpenCV, a popular computer vision library in Python. The main objective is to detect vehicles passing through a predefined line in a video feed and count them accurately. Here’s a detailed description of the system and its components:

Key Components and Workflow
Video Capture:

The system captures video frames from a video file (video.mp4) using OpenCV's VideoCapture function.
Preprocessing:

Frames are converted to grayscale to simplify the computational process.
Gaussian blur is applied to reduce noise and improve contour detection.
Background Subtraction:

The cv2.bgsegm.createBackgroundSubtractorMOG() method is used to subtract the background and detect moving objects, in this case, vehicles.
Morphological Operations:

Dilatation and morphological closing operations are applied to fill gaps and enhance the contours of the detected objects.
Contour Detection:

Contours of the detected objects are found using cv2.findContours().
Only contours with a minimum width and height (specified by min_width_rect and min_height_rect) are considered valid vehicles.
Vehicle Detection and Counting:

For each valid contour, a bounding rectangle is drawn around the detected vehicle.
The center of the vehicle is calculated and stored in a list.
If the center crosses a predefined counting line (within a specified offset), the vehicle count is incremented.
The counting line is dynamically updated to indicate vehicle detection visually.
Display and Output:

The processed frames are displayed in a window with bounding rectangles around detected vehicles and the current vehicle count.
Vehicle count is displayed on the video feed.
Performance Control:

The frame processing is controlled by a delay to manage the speed of the video processing loop, ensuring it runs at a manageable pace.
