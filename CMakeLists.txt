cmake_minimum_required(VERSION 3.1)
project(mc_rtc_msgs VERSION 1.0.0)

find_package(catkin REQUIRED COMPONENTS roscpp message_generation geometry_msgs)

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

generate_messages(DEPENDENCIES geometry_msgs)

catkin_package(
  INCLUDE_DIRS include
  CATKIN_DEPENDS geometry_msgs
)

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h")
