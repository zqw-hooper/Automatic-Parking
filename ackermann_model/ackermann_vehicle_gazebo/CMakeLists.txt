cmake_minimum_required(VERSION 2.8.3)
project(ackermann_vehicle_gazebo )
find_package(catkin REQUIRED COMPONENTS rospy)
catkin_package(
        DEPENDS
        CATKIN_DEPENDS rospy 
        )


file(GLOB PYTHON_SCRIPTS RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}"
        "${CMAKE_CURRENT_SOURCE_DIR}/nodes/${PROJECT_NAME}/*.py")
install(PROGRAMS ${PYTHON_SCRIPTS}
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
file(GLOB PYTHON_SCRIPTS_COMMANDER RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}"
        "${CMAKE_CURRENT_SOURCE_DIR}/nodes/${PROJECT_NAME}/commander/*.py")
install(PROGRAMS ${PYTHON_SCRIPTS_COMMANDER}
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})