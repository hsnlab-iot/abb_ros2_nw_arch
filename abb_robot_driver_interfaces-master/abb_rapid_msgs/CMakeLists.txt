cmake_minimum_required(VERSION 3.5)

# CMake project
project(abb_rapid_msgs)

# Find ament dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

# Define message files
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ConfData.msg"
  "msg/ExtJoint.msg"
  "msg/JointTarget.msg"
  "msg/LoadData.msg"
  "msg/Orient.msg"
  "msg/Pos.msg"
  "msg/Pose.msg"
  "msg/RobJoint.msg"
  "msg/RobTarget.msg"
  "msg/ToolData.msg"
  "msg/WObjData.msg"
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
