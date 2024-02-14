cmake_minimum_required(VERSION 3.5)
project(mc_rtc_msgs VERSION 1.1.1)

if(NOT DEFINED ENV{ROS_VERSION})
  message(FATAL_ERROR "ROS_VERSION is not set in the environment")
endif()

if($ENV{ROS_VERSION} EQUAL 1)
  find_package(catkin REQUIRED COMPONENTS message_generation geometry_msgs)

  add_service_files(
    DIRECTORY srv
    FILES
    EnableController.srv
    open_grippers.srv
    close_grippers.srv
    set_gripper.srv
    get_joint_pos.srv
    set_joint_pos.srv
    play_next_stance.srv
    send_msg.srv
    send_recv_msg.srv
    move_com.srv
  )

  add_message_files(
    DIRECTORY msg
    FILES
    JointSensors.msg
  )
  generate_messages(DEPENDENCIES geometry_msgs)

  catkin_package(
    CATKIN_DEPENDS geometry_msgs
  )

  install(DIRECTORY include/${PROJECT_NAME}/
    DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
    FILES_MATCHING PATTERN "*.h")
elseif($ENV{ROS_VERSION} EQUAL 2)
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
else()
  message(FATAL_ERROR "Unknown ROS version: $ENV{ROS_VERSION}")
endif()
