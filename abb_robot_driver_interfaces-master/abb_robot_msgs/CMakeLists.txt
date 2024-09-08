cmake_minimum_required(VERSION 3.5)

# CMake projekt
project(abb_robot_msgs)

# Find ament dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

# Define message files
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/MechanicalUnitState.msg"
  "msg/RAPIDSymbolPath.msg"
  "msg/RAPIDTaskState.msg"
  "msg/ServiceResponses.msg"
  "msg/SystemState.msg"
  "srv/GetFileContents.srv"
  "srv/GetIOSignal.srv"
  "srv/GetRAPIDBool.srv"
  "srv/GetRAPIDDnum.srv"
  "srv/GetRAPIDNum.srv"
  "srv/GetRAPIDString.srv"
  "srv/GetRAPIDSymbol.srv"
  "srv/GetRobotControllerDescription.srv"
  "srv/GetSpeedRatio.srv"
  "srv/SetFileContents.srv"
  "srv/SetIOSignal.srv"
  "srv/SetRAPIDBool.srv"
  "srv/SetRAPIDDnum.srv"
  "srv/SetRAPIDNum.srv"
  "srv/SetRAPIDString.srv"
  "srv/SetRAPIDSymbol.srv"
  "srv/SetSpeedRatio.srv"
  "srv/TriggerWithResultCode.srv"
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
