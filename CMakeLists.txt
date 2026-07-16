cmake_minimum_required(VERSION 3.22)
project(mc_rtc_msgs VERSION 1.1.3)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
msg/ros2/JointSensors.msg
srv/ros2/CloseGrippers.srv
srv/EnableController.srv
srv/ros2/GetJointPos.srv
srv/ros2/MoveCoM.srv
srv/ros2/OpenGrippers.srv
srv/ros2/PlayNextStance.srv
srv/ros2/SendMsg.srv
srv/ros2/SendRecvMsg.srv
srv/ros2/SetGripper.srv
srv/ros2/SetJointPos.srv
DEPENDENCIES geometry_msgs
)

install(DIRECTORY include/
DESTINATION include/${PROJECT_NAME}
FILES_MATCHING PATTERN "*.h")

ament_package()
