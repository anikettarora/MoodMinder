# Mood Minder 😃

Mood Minder is an innovative emotion detection system that leverages real-time facial recognition to identify and classify user emotions. Built using Python and deep learning frameworks, this project aims to enhance user interaction through personalized experiences based on detected emotions.

## Architecture

Here's how the Mood Minder system works:

1. **Data Collection**: 
   - The process kicks off by capturing real-time video feed from your webcam using OpenCV. 
   - With the help of MediaPipe, we detect facial landmarks and hand gestures. As you perform different expressions, the system collects data points (facial and hand coordinates) and saves them in a structured format. You simply name the expression you're recording, and it generates a `.npy` file containing the data for that expression.

2. **Training the Model**: 
   - Once we have enough samples for various expressions, it's time to train our model! 
   - We load all the recorded data, shuffle it for randomness, and prepare it for training. A neural network is built using Keras, consisting of dense layers that learn to associate the features of your expressions with their corresponding labels. The model is trained over 50 epochs to improve accuracy, using categorical cross-entropy as the loss function.

3. **Real-Time Inference**:
   - After training, we can use the model to detect emotions in real-time! 
   - As you perform different expressions in front of the camera, the system processes the input in the same way it did during training. It predicts which emotion you’re displaying and overlays the result on the webcam feed.

## Installation

   ```bash
   pip install -r requirements.txt

   python data_collection.py
   python data_training.py
   python inference.py 
