cmake_minimum_required(VERSION 3.5)
project(image_conversion)

find_package(ament_cmake REQUIRED)
find_package(rclpy REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(cv_bridge REQUIRED)
find_package(OpenCV REQUIRED)
find_package(std_msgs REQUIRED)
find_package(std_srvs REQUIRED)

add_executable(image_conversion_node src/image_conversion_node.py)

ament_target_dependencies(
  image_conversion_node
  rclpy
  sensor_msgs
  cv_bridge
  OpenCV
  std_msgs
  std_srvs
)

install(TARGETS
  image_conversion_node
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
