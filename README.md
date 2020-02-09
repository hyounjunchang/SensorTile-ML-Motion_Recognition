# Motion Recognition using Sensortile through ML

This project was for UCLA's E96C: Internet of Things.
We were provided with EmbeddedML Neural Network model that was modified by Charles Zaloom. All work was done through STMicroelectronics' System Workbench.

Link to UCLA's curriculum: https://sites.google.com/view/ucla-stmicroelectronics-iot/home

No changes were made to the Machine Learning model itself. The only modifications were done in /Src/main.c

## Demonstration

Video: https://www.youtube.com/watch?v=_7uiGiuSXCs&feature=emb_title

Demonstration Slides: https://docs.google.com/presentation/d/13HSkLg0Jfvj6XgC18O9jmh_JaKgCFAjuk92LafDlY24/edit?usp=sharing

## How the Motion Detection Works

The motion that is being detected has two stages; It could be a vertical movement followed by leftward turn, rightward turn followed by downward movement, and etc.

Six motions (that would be recognized) will be initially set up, and the EmbeddedML Neural Network will train to detect the motions.

We used an accelerometer and a gyroscope to detect the features in the motions. The first feature would be extracted through an accelrometer, calulating the change in acceleration due to gravity (as different orientation would result in different readings in X,Y, and Z axis). The second feature would be extracted through a Gyroscope, checking if the controller rotated above a certain threshold (using integral of angular speed to detect total angle traveled).

## Shortcomings

The ML model is not able to detect a difference between a variety of motions due to lack of data it intakes. (It is not able to detect motions that are not drastically different). 

The interface to setup the motion detection is not intuitive either due to the sensortile's lack of LCD screen.

The Matrix used for ML only uses 3 elements (opposed to 6 inputs we extract from the 2 features). Due to the time constraint of the project, no modifications were done to the ML model. Adjusting the ML model to take more inputs (in the input matrix) would most likey fix the shortcomings.

Despite these shortcomings, we still found this project a nice introduction to ML and microcontroller programming!

Project by: Hyounjun Chang, Ryan Tong
