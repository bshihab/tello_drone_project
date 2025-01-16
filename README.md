# Tello Drone Control Project

This project provides a comprehensive set of Python scripts for controlling a DJI Tello drone, enabling various functionalities like basic movements, image capture, keyboard control, color-based line following, and even basic mapping.

## Project Overview

The project is structured into several Python files, each responsible for a specific aspect of drone control:

-   **`basic_movements.py`**: Demonstrates fundamental drone movements (takeoff, landing, forward, and rotational movement) using the `djitellopy` library.
-   **`image_capture.py`**: Captures and displays live video feed from the drone's camera using `djitellopy` and `cv2`.
-   **`keyboard_control.py`**: Enables manual control of the drone using keyboard inputs, utilizing a custom `keypress_module` for key detection.
-   **`keypress_module.py`**: A utility module that uses `pygame` to detect and return the state of specific keyboard keys.
-   **`LineFollower.py`**: Implements a line-following algorithm that allows the drone to follow a path based on color detection. It uses HSV color thresholding and contour detection to identify the line and adjust the drone's movement accordingly.
-   **`mapping.py`**: A basic mapping script that tracks the drone's position based on keyboard inputs and visualizes its path on a simple map.
-   **`ColorPicker.py`**: A utility to help determine the correct HSV color range values for the line-following algorithm.

## Dependencies

This project relies on the following Python libraries:

-   **`djitellopy`**: A Python library for interacting with the DJI Tello drone.
-   **`opencv-python` (cv2)**: Used for image processing, video capture, and display.
-   **`pygame`**: Used for keyboard input detection in `keypress_module.py`.
-   **`numpy`**: Used for numerical operations, especially in image processing and calculations.

You can install these dependencies using pip:

pip install djitellopy opencv-python pygame numpy


## Usage

### Basic Movements

Run `basic_movements.py` to see the drone perform a simple sequence of actions: takeoff, move forward, rotate, and land.

### Image Capture

Execute `image_capture.py` to view the live video stream from the drone's camera.

### Keyboard Control

1. Run `keyboard_control.py` to control the drone with your keyboard.
2. Use the following keys:
    -   **Arrow keys**: Forward, backward, left, right movement.
    -   **W/S**: Up and down movement.
    -   **A/D**: Yaw (rotation) left and right.
    -   **Q**: Land the drone.
    -   **E**: Takeoff.

### Line Following

1. Use `ColorPicker.py` to determine the HSV values for the line you want the drone to follow. Adjust the trackbars to isolate the line color and note down the HSV values displayed in the console.
2. Update the `hsvVals` list in `LineFollower.py` with the values you obtained from `ColorPicker.py`.
3. Run `LineFollower.py` to start the line-following behavior. The drone will attempt to follow the detected line.

### Mapping

1. Run `mapping.py` to start the mapping process.
2. Control the drone using the keyboard (similar to `keyboard_control.py`).
3. The script will display a window showing the drone's estimated path based on your inputs.

## Notes

-   Ensure your Tello drone is powered on and connected to your computer's Wi-Fi network before running any of these scripts.
