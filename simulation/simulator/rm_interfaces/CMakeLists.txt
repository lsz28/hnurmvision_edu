cmake_minimum_required(VERSION 3.8)
project(rm_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(builtin_interfaces REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Armor.msg"
  "msg/Armors.msg"
  "msg/ChassisCmd.msg"
  "msg/DebugArmor.msg"
  "msg/DebugArmors.msg"
  "msg/DebugLight.msg"
  "msg/DebugLights.msg"
  "msg/DebugRuneAngle.msg"
  "msg/GimbalCmd.msg"
  "msg/JudgeSystemData.msg"
  "msg/Measurement.msg"
  "msg/OperatorCommand.msg"
  "msg/PlanGimbalCmd.msg"
  "msg/Point2d.msg"
  "msg/RuneTarget.msg"
  "msg/SerialReceiveData.msg"
  "msg/Target.msg"
  "msg/VisionReceiveData.msg"
  "msg/VisionSendData.msg"
  "srv/RunHandEyeCalibration.srv"
  "srv/SetMode.srv"
  DEPENDENCIES
    std_msgs
    geometry_msgs
    builtin_interfaces
)

ament_export_dependencies(rosidl_default_runtime)
ament_package()
