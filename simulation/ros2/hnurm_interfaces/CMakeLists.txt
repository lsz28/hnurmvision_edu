cmake_minimum_required(VERSION 3.8)
project(hnurm_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

rosidl_generate_interfaces(
  ${PROJECT_NAME}
  "msg/armor/Target.msg"
  "msg/armor/TrackerInfo.msg"
  "msg/detect/ArmorArray.msg"
  "msg/detect/Armor.msg"
  "msg/detect/ArmorType.msg"
  "msg/detect/Light.msg"
  "msg/detect/Point2D32.msg"
  "msg/uart/BulletSpeed.msg"
  "msg/uart/SelfColor.msg"
  "msg/uart/TargetState.msg"
  "msg/uart/TargetType.msg"
  "msg/uart/VisionRecvData.msg"
  "msg/uart/VisionSendData.msg"
  "msg/uart/WorkMode.msg"
  "srv/SetSelfColor.srv"
  "srv/SetWorkMode.srv"
  DEPENDENCIES ${${PROJECT_NAME}_FOUND_BUILD_DEPENDS}
)

ament_auto_package()
