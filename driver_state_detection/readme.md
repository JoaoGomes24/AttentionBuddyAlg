# Attention Monitoring System with ELMO Robot

## Overview
In our project, we have innovatively adapted the "Real Time Driver State Detection" system, originally intended for driver attention monitoring, for a novel application in educational settings, in this project we analyze facial features in real-time through a webcam. The core objective of this system is to detect distractions during reading sessions by closely observing eye movements and facial positions.

The system operates by continuously monitoring the reader's attention level as they interact with text. Upon detecting any signs of distraction, it queries the robot ELMO which provides feedback, thereby aiding in refocusing and enhancing the overall reading experience.

Our project exemplifies the adaptability of computer vision and machine learning technologies, showcasing their potential not just in immediate task improvement but also in their broader applicability in educational innovations.


## System Requirements
- Python 3.9
- Anaconda
- Git
- Pip
- Libraries: OpenCV, NumPy, MediaPipe, gtts, pydub, PyQT5
- Recommended OS: Ubuntu 18.04 for optimal ELMO robot performance
- Webcam for real-time attention detection

## Setup and Installation
1. **Python Libraries Installation:**
   ```bash
   pip install opencv-python numpy mediapipe gtts pydub PyQT5

2. **Prepare ELMO V2 Robot:**
    * First to getting started with ELMO is necessary to follow a Elmo Guide, that were made available to us in the course page
    * Then, ensure that the ELMO robot is set up with the necessary software and is connected to the same network as the computer running the attention monitoring system, by ethernet cables.
    * Finaly you need to know ELMO IP address, in our case it was "192.168.0.102"

3. **Ubuntu Setup for SCP Commands:**
    To upload files (sounds and videos) to the ELMO robot, Ubuntu 18.04 is recommended. Install and configure SSH and SCP on your Ubuntu system.

4. **Clone the Repository:**
    ```bash
    git clone [repository_url]
    cd [repository_directory]

5. **File Preparation:**
    Place the required sound and video files in the elmo-v2/src/static directory on your Ubuntu system. These files will be uploaded to the ELMO robot.

6. **Running the SCP Commands:**
    Use the provided Python scripts to upload the sound and video files to the ELMO robot. Ensure the robot's IP address is correctly specified in the scripts.

## Running the Attention Monitoring System

1. **Start the System:**
    Open a PowerShell window as administrator on a Windows system (Ubuntu 18.04 is used for SCP commands only).

2. **Run the Main Script:**
    Navigate to the directory containing main.py and execute:

    ```bash
    python main.py

This script starts the webcam and begins monitoring the user's attention using computer vision algorithms. Distractions are detected based on eye movements and facial positions.

3. **ELMO Robot Interaction:**
    The ELMO robot responds to detected distractions by displaying videos and playing sound files. The robot's reactions aim to refocus the user's attention.

4. **Monitoring Output:**
    The system provides real-time visual feedback on the user's attention state, including EAR (Eye Aspect Ratio) scores, gaze direction, and head pose.

## Understanding the Code Structure

* Main.py: Implements the attention detection algorithm using OpenCV and MediaPipe. Connects with the ELMO robot for interactive responses.
* ElmoV2API: Contains functions to control the ELMO robot, including playing sounds and videos, and setting volume.
Utils: Helper functions for the attention detection algorithm.
* Eye_Dector_Module, Pose_Estimation_Module, Attention_Scorer_Module: Modules for specific functionalities in attention detection.