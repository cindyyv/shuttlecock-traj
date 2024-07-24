# Shuttlecock Trajectory Prediction System

This project explores the development and application of an innovative system that integrates computer vision and automated machinery to precisely target and launch badminton shuttlecocks. 

## Objective 
We want to create a tool that can provide educational insight and assist in sports training by providing consistent and accurate shuttlecock delivery. We employed a dual camera setup, ellipse detection, and trajectory prediction connected to a machine capable of adjusting velocity and angles to launch a shuttlecock to the target swiftly. The results demonstrated a high degree of precision in shuttlecock targeting and launching, with potential applications in athlete training and sports analytics. Future work will focus on enhancing the system's and further refine its accuracy and user interaction.

## Introduction
In recent years, the fusion of technology with sports training has opened new ways to enhance athletic performance. Among these technological advancements, the application of computer vision and automated machinery in sports presents an opportunity to revolutionize training methods. This project introduces an innovative system designed to target and launch badminton shuttlecocks using computer vision algorithms, precise trajectory prediction, and mechanical controls.

The core of the system lies in its ability to accurately detect a designated target using image processing techniques. This is coupled with an automated mechanism capable of adjusting the speed and angles to launch the shuttlecock to follow a predicted trajectory, thereby simulating various playing conditions. By providing a controlled and adjustable environment, the system can aid players in focusing on particular aspects of their game, from reaction time to strategic play. Additionally, scholars might also benefit from using the system to aid them in sports analytics and development.

## Methods
### Dual Camera Setup
Two cameras are set up on the ceilings of a lab, providing two different perspectives. Inside the lab is a mini-sized badminton court designed to mimic half of the play court. The user can use the UI interface to calibrate the cameras to follow the space of the imitative court, providing a 3D space with the middle point of the court as the zero-point (0,0,0).

### Ellipse Detection Algorithm
The original picture is passed on to the algorithm, which converts the image to HSV color space and applies thresholding to create a mask. It then applies Gaussian blur to the mask, highlights the difference in intensity by calculating the absolute difference between the mask and the blurred version, uses a Canny algorithm to detect the edges, and finally uses a Hough circle to detect the ellipse in the picture.

### 3D Plane Trajectory Prediction
Each camera runs the detection algorithm to find the 2D coordinates of the ellipse. Using the extrinsic matrix of the camera, the two points are triangulated into the 3D space, resulting in the 3D coordinates of the ellipse. Trajectory calculation starts with a certain velocity and incline range. The numerical 3D trajectory of a shuttlecock is simulated using ordinary differential equations (ODEs), accounting for air drag, gravity, and the velocity of the shuttlecock.

## Procedures
1. Run main file to access the main UI interface.
2. Enter the 3D coordinates of the shuttlecock launcher machine relative to the court.
3. Ensure the cameras detect the target ellipse. A green rectangle indicator will show up on the target.
4. For a single shot, click the ‘Config’ button to receive velocity, yaw, and pitch values for the launch.
5. For continuous shots, set the interval and press the “Start” button to begin launching shuttlecocks at regular intervals.

## Results
The experiment achieved an accuracy score of approximately 90%. The target detection may not always return an accurate depiction of the whole target, and while a threshold is set, the limitations of the algorithm and inconsistent conditions of the machine positioning and target can result in inaccurate launches. Future improvements could enhance algorithm performance and test conditions.

## Conclusion
This project successfully integrates computer vision and automated machinery to create a system capable of targeting and launching badminton shuttlecocks with high precision. The system enhances the quality and efficiency of badminton training and offers valuable insights into robotics and AI applications in sports. Future enhancements will focus on increasing adaptability to various environmental conditions and improving user interfaces for broader training applications.
