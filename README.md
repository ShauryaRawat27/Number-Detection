Hand Gesture Number Detection (1 to 5) using OpenCV
This project utilizes OpenCV for image preprocessing to detect numbers from 1 to 5 in live videos and images. 
It is designed to recognize digits (1 to 5) from images or live webcam feeds .
This project detects numbers 1 to 5 based on hand gestures using OpenCV. The system calculates the maximum distance from the center of the hand and compares it to a threshold to count the number of fingers being held up. The model does not require pre-trained models on digits but uses simple hand geometry (distance calculation) for number recognition.

OpenCV handles hand detection and image preprocessing.
Scikit is also used in many aspects of the code.
The detection relies on the geometry of the hand, where the number of fingers raised corresponds to the number being detected (1 through 5).

How it Works

1.Hand Detection:

->The first step involves detecting the hand in the image or video frame. This is achieved using OpenCV's contour detection.
->A mask is created to isolate the hand, and findContours is used to identify the contours of the hand.

2.Center of the Hand:

->Once the hand is detected, the centroid (center) of the hand is calculated. This serves as the reference point for measuring the distances of different points (finger tips) from the center of the hand.

3.Maximum Distance Calculation:

->For each fingertip (detected as a contour point), the Euclidean distance from the hand center is calculated.
->If the distance of a fingertip from the center exceeds a threshold, it is considered as a raised finger. The number of raised fingers is counted to determine the number between 1 to 5.

4.Thresholding and Counting Fingers:

->A threshold distance is defined. If the fingertip is farther than this threshold from the center, it is counted as one finger.
->Based on how many fingers are detected, a corresponding number is predicted (e.g., 1 finger corresponds to the number "1", 2 fingers to "2", and so on).

5.Real-Time Prediction:
->For live webcam detection, the system processes each frame in real-time and displays the detected number on the video feed.
