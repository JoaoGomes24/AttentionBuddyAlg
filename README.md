# Attention Monitoring System with ELMO Robot

## Overview
Our project innovatively adapts the "Real Time Driver State Detection" system, from(https://github.com/e-candeloro/Driver-State-Detection), initially designed for driver attention monitoring, to the context of educational settings. This system analyzes facial features in real-time through a webcam to detect distractions during reading sessions. As readers interact with text, the system continuously monitors their attention level, and upon detecting distractions, queries the ELMO robot for feedback. This method aids in refocusing and enhancing the reading experience, showcasing the adaptability of computer vision and machine learning in educational technology.

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
    * Follow the Elmo Guide provided in the course to set up the ELMO robot
    * Ensure the ELMO robot is connected to the same network as your computer via Ethernet.
    * Finaly you need to know ELMO IP address, in our case it was "192.168.0.102"

3. **Ubuntu Setup for SCP Commands:**
    * To upload files (sounds and videos) to the ELMO robot, Ubuntu 18.04 is recommended. Install and configure SSH and SCP on your Ubuntu system.

4. **Clone the Repository:**
    * This is done into your powershell command line.
    ```bash
    git clone https://github.com/JoaoGomes24/AttentionBuddyAlg.git
    cd AttentionBuddyAlg

5. **Unzip ELMO files:**
    * In the zip submitted there is a "elmo-v2.zip", unzip it in a way to have it in your ubuntu environment.
    * Also unzip it again into the folder AttentionBuddyAlg/driver_state_detection, in powershell command line.

6. **Small Modification**
    * In your cloned folder, AttentionBuddyAlg, go into driver_state_detection/elmo-v2/src and change "elmo_test.py" with the file that is inside the zip submitted name "elmo_test.py"

## Set up the ELMO robot with the necessary files.

1. **Start the System:**
    * On Ubuntu 18.04, navigate to 'elmo-v2/src/elmo_test.py'. 

2. **Run the Test Script:**

    ```bash
    python3 elmo_test.py {ip_address_of_elmo}

With the files from the zip, in your Ubuntu 18.04 environment, after running this command you will have the robot ready to be used.

## Running the Attention Monitoring System

1. **Start the System:**
    Open a PowerShell window as administrator on a Windows system (Ubuntu 18.04 is used only to send SCP commands).

2. **Run the Main Script:**
    Navigate to the directory containing 'AttentionBuddyAlg/driver_state_detection/main.py' and execute:

    ```bash
    python main.py

Note: You may have to change the "robot_ip = "192.168.0.102""(line 47 of AttentionBuddyAlg/driver_state_detection/elmo-v2/src/elmo_test.py)  or the lines(238,247,261,273) inside AttentionBuddyAlg/driver_state_detection/main.py, to the right IP of the robot. We used ELMO 2 so we just hardcoded this part.

This script starts the webcam and begins monitoring the user's attention using computer vision algorithms. Distractions are detected based on eye movements and facial positions.

3. **ELMO Robot Interaction:**
    The ELMO robot responds to detected distractions by displaying different eyes and playing sound files. The robot's reactions aim to refocus the user's attention.

4. **Monitoring Output:**
    The system provides real-time visual feedback on the user's attention state, including EAR (Eye Aspect Ratio) scores, gaze direction, and head pose.


## Understanding the Code Structure

* Main.py: Implements the attention detection algorithm using OpenCV and MediaPipe. Connects with the ELMO robot for interactive responses.
* AttentionBuddyAlg/driver_state_detection/elmo-v2/src/elmo_test.py: Contains functions to control the ELMO robot, including playing sounds and videos, and setting volume.
* elmo-v2/src/elmo_test.py: Contains functions to send to ELMO robot the sounds and eyes it will display in the experiment.