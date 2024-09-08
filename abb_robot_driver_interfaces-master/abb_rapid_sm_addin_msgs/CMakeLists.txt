cmake_minimum_required(VERSION 3.5)

# CMake projekt
project(abb_rapid_sm_addin_msgs)

# Find ament dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(abb_rapid_msgs REQUIRED)

# Define message files
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/EGMActivateSettings.msg"
  "msg/EGMRunSettings.msg"
  "msg/EGMSettings.msg"
  "msg/EGMSetupSettings.msg"
  "msg/EGMStopSettings.msg"
  "msg/RuntimeState.msg"
  "msg/StateMachineState.msg"
  "srv/GetEGMSettings.srv"
  "srv/SetEGMSettings.srv"
  "srv/SetRAPIDRoutine.srv"
  "srv/SetSGCommand.srv"
  DEPENDENCIES std_msgs abb_rapid_msgs
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
