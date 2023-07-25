# Deadlift Rep Counter

This project uses OpenCV and MediaPipe to count reps when doing deadlifts. It tracks the user's pose and detects when they move from the down position to the up position, incrementing a counter.

## Usage

Run the code and stand in view of the webcam. Get into the starting deadlift position with the bar on the ground. Then pick up the bar to complete one rep. Put it back down and repeat. The counter will increment each time you lift the bar from the down position to the up position.

## Code Overview

- Imports the necessary packages like OpenCV, Mediapipe, Tkinter, etc.

- Sets up the Tkinter GUI with labels to display the current stage (up/down), rep count, and pose detection probability.

- Loads a pickled Random Forest classifier model trained to detect the up and down deadlift poses.

- Initializes OpenCV video capture from the webcam.

- The `detect()` function:
  - Reads a frame from the webcam
  - Runs Mediapipe pose detection
  - Passes the pose landmarks to the classifier
  - Checks the predicted class and probability to determine the current stage
  - Increments the counter when stage changes from down to up
  - Displays the current stage, count, and probability on the GUI

- Main loop repeatedly calls `detect()` to process each video frame 

## Credits

- Mediapipe for pose detection 
- Scikit-learn for Random Forest model
- Tkinter for simple GUI

