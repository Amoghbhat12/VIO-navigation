# VIO-Based Navigation System in GPS-Denied Environments

A mini-project focused on implementing a robust sensor fusion framework for autonomous navigation in environments where GPS is unreliable or unavailable.

## 🚀 Project Overview

In environments like tunnels, dense urban areas, or during satellite jamming, GPS becomes unreliable. This project integrates **Visual Odometry (VO)** and **Inertial Odometry (IO)** using a **Kalman Filter** to accurately estimate position and orientation.

![WhatsApp Image 2025-06-26 at 20 05 27_02502cb4](https://github.com/user-attachments/assets/9c7de0b5-2ae5-4a67-97f6-4444800fb68a)

## 🎯 Objectives

- Develop a navigation system combining camera and IMU data.
- Use **ORB (Oriented FAST and Rotated BRIEF)** for feature extraction in visual odometry.
- Reduce drift and enhance robustness with **Extended Kalman Filter (EKF)**.
- Achieve reliable tracking in GPS-denied settings.

## 🔧 System Architecture

- **IMU**: MPU-6050 for acceleration and angular velocity.
- **Camera**: RGB camera capturing 1080p @ 30-60 FPS.
- **Sensor Fusion**: Timestamp synchronization and fusion using EKF.
- **State Vector**: `[x, y, z, vx, vy, vz]`

## 📊 Optimization Method

Implemented **Extended Kalman Filter** (EKF) to handle non-linearities in sensor data fusion. EKF updates the system's state recursively with Gaussian noise assumptions, balancing efficiency and accuracy.

## 📈 Results Summary

| Segment           | Ground Truth | Without EKF | With EKF |
|------------------|--------------|-------------|----------|
| First 5 m        | 5 m          | 7 m         | 5 m      |
| Next 5 m         | 5 m          | 6 m         | 6 m      |
| Left deviation   | 5 m          | 9 m         | 7 m      |
| Final 5 m        | 5 m          | 7 m         | 5 m      |
| **Total Distance** | 20 m         | 29 m        | 23 m     |

✅ EKF reduced drift and improved positional accuracy significantly.
Accuracy = 86.96%

## 💡 Applications

- Disaster search and rescue operations
- Autonomous vehicle navigation in urban areas
- Drone delivery in signal-jammed zones
- Medical logistics in remote regions


