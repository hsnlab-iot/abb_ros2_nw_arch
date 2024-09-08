cmake_minimum_required(VERSION 3.5)

# CMake projekt
project(abb_egm_msgs)

# Find ament dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

# Define message files
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/EGMChannelState.msg"
  "msg/EGMState.msg"
  DEPENDENCIES std_msgs
)

# Install additional files

install(
  FILES
    LICENSE
    README.md
  DESTINATION
    share/${PROJECT_NAME}/
)

ament_package()
