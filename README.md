Here's a README file for your project that explains the `HandDetectionModule.py` and `PingPongGame.py` files:

---

# Ping Pong Game with Hand Detection

## Overview

This project is a simple Ping Pong game where the paddle's position is controlled by hand movements detected through a webcam. The game is implemented in Python using OpenCV and MediaPipe.

## Files

### 1. `HandDetectionModule.py`

This module handles hand detection using the MediaPipe library.

#### Dependencies

- `cv2` (OpenCV)
- `numpy`
- `mediapipe`

#### Classes

**`MediapipeLandmark`**: A class for detecting hand landmarks using MediaPipe.

- **Methods**:
  - `__init__(self, max_num_hands=2, model_complexity=1, min_detection_confidence=0.5, min_tracking_confidence=0.5)`: Initializes the MediaPipe hand detection model with specified parameters.
  - `Coordinates(self, frame)`: Processes a given frame to detect hand landmarks and returns the x-coordinate of the 8th landmark (index finger tip) scaled to the frame width.

### 2. `PingPongGame.py`

This script implements a classic Ping Pong game where the paddle's position is controlled by hand movement detected through the `HandDetectionModule`.

#### Dependencies

- `cv2` (OpenCV)
- `numpy`
- `HandDetectionModule` (custom module)

#### Parameters

- **Game Window**:
  - `width`, `height`: Dimensions of the game window.
  - `paddlewidth`, `paddleheight`: Dimensions of the paddle.
  - `paddlecolor`: Color of the paddle.
  - `lives`: Number of lives the player starts with.
  - `deltax`, `deltay`: Movement deltas for the ball.
  - `xpos`, `ypos`: Initial position of the ball.
  - `level`, `ballradius`, `bgcolor`, `scorecolor`: Game level, ball radius, background color, and score color.

#### Functionality

- **Webcam Setup**: Initializes the webcam and configures the frame properties.
- **Game Loop**: 
  - Captures frames from the webcam.
  - Uses `MediapipeLandmark` to get the hand's x-coordinate and controls the paddle position.
  - Handles ball movement and collision with the paddle and walls.
  - Updates score, level, and lives.
  - Displays the game state and messages.

#### How to Run

1. Ensure you have the required dependencies installed:
    ```bash
    pip install opencv-python numpy mediapipe
    ```

2. Run the game script:
    ```bash
    python PingPongGame.py
    ```

3. Follow the on-screen instructions to play the game. The paddle will move according to the detected hand position.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [OpenCV](https://opencv.org/) for computer vision functionalities.
- [MediaPipe](https://mediapipe.dev/) for hand landmark detection.

---

Feel free to adjust or expand on any sections based on your specific needs!
