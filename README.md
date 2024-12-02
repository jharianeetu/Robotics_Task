# ROS 2 Image Conversion Node

## Objective

This ROS 2 package converts images from a USB camera into either grayscale or color, based on a mode selected via a ROS 2 service.

## Installation

1. Clone the repository into your workspace:
   ```bash
   cd ~/ros2_ws/src
   git clone https://github.com/your-username/image_conversion.git

2.Install dependencies:
   sudo apt install ros-humble-usb-cam
   pip install opencv-python cv-bridge

3.Build the workspace:
  cd ~/ros2_ws
  colcon build

4.Source the workspace:
  source install/setup.bash


## Usage
1.Launch the nodes:
  ros2 launch image_conversion image_conversion_launch.py

2.Call the service to switch modes:
  a. Grayscale Mode:
  ros2 service call /image_conversion/set_conversion_mode std_srvs/srv/SetBool "{data: true}"

  b. Color Mode:
  ros2 service call /image_conversion/set_conversion_mode std_srvs/srv/SetBool "{data: false}"

3.View the processed image:
ros2 topic echo /converted_image

