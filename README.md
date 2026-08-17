# Interactive MRI Comfort System

Bachelor thesis project in Computer Engineering and Information Technology at Western Norway University of Applied Sciences (HVL), developed in collaboration with NordicNeuroLab.

## Overview

This project explored how interactive entertainment can improve patient comfort during MRI examinations. MRI scans often require patients to lie still in a narrow and noisy environment for an extended period of time, which can be stressful, especially for children and patients with claustrophobia.

The goal of the project was to design, implement, and evaluate a prototype of an interactive MRI comfort system. Instead of only offering passive entertainment such as video or music, the system allows patients to interact with simple games using MRI-compatible or potentially MRI-compatible input methods.

The project focused on evaluating three input modalities:

* Eye tracking
* Voice control
* Fiber-optic physical buttons

## Problem Statement

The main research question of the bachelor thesis was:

> Which input method is best suited to improve the patient experience during MRI examinations?

To answer this, the project investigated how different input methods could be implemented in an interactive MRI comfort system, what technical and practical challenges arise in an MRI-like environment, and how the input methods differ in usability and feasibility.

## Prototype

The developed prototype is a web-based interactive entertainment system with support for multiple input methods. It includes simple game-based experiences designed to keep the user engaged without encouraging excessive movement during the MRI scan.

The prototype included:

* A quiz-based interaction system
* A simple PongBreaker-style game
* Eye-controlled interaction using gaze tracking
* Voice-controlled interaction using predefined commands
* Button-based interaction through serial input and WebSocket communication

## Input Methods

### Eye Tracking

Eye tracking was implemented using WebGazer.js and jsPsych. The system used webcam-based gaze tracking, calibration, smoothing, and a dwell-click mechanism where users could select interface elements by looking at them for a short period of time.

This approach had strong accessibility potential, but was technically challenging due to calibration sensitivity, gaze instability, and the need for reliable cursor control.

### Voice Control

Voice control was implemented using a local client-server architecture. Audio from the browser was streamed through WebSocket to a local Python server running Vosk for speech recognition. The system recognized predefined commands such as menu selections and quiz answers.

This method showed potential under moderate noise conditions, but MRI-like background noise created challenges for reliable speech recognition.

### Fiber-Optic Physical Buttons

The physical button solution was based on NordicNeuroLab’s fiber-optic Response Grips. Button signals were handled through serial communication and translated into application commands using a Node.js middleware layer and WebSocket communication.

During development, serial input was also simulated using `socat` when physical hardware was not available.

## Technologies Used

* HTML5
* CSS3
* JavaScript
* Node.js
* Python
* WebSocket
* WebGazer.js
* jsPsych
* Vosk speech recognition
* Serial communication
* socat
* GitHub Projects
* Figma / Wireframing tools

## Evaluation

The system was evaluated through both technical and functional testing.

The technical evaluation focused on:

* Eye-tracking accuracy
* Voice-recognition performance under simulated MRI noise
* Responsiveness of button-based input
* Robustness of the implemented input methods

The functional evaluation focused on:

* Usability
* Patient comfort
* Control feeling
* Practical feasibility in an MRI-like environment
* Feedback from NordicNeuroLab and a radiographer

## Main Findings

The evaluation showed that physical buttons were the most robust and clinically feasible input method overall. They provided high reliability, strong MRI compatibility, and low technical risk.

Voice control showed promise, especially under moderate noise conditions, but required better noise handling and microphone placement before it could be considered reliable in a real MRI setting.

Eye tracking had high accessibility potential, but was the most technically challenging method due to calibration issues and unstable gaze control. In its current form, it was considered less suitable for clinical use than the other input methods.

## Repository Content

This repository contains the bachelor thesis report:

[Read the full bachelor thesis report](bachelor-thesis-report.pdf)

## Authors

* Sondre Risnes
* Mats Øinas
* Marius Horn
* Adam Yasaev

## Institution

Western Norway University of Applied Sciences
Department of Computer Science, Electrical Engineering and Mathematical Sciences
Bachelor in Computer Engineering and Information Technology

## Collaboration Partner

NordicNeuroLab

## Supervisor

Patrick Stünkel
