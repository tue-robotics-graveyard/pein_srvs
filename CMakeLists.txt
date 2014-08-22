cmake_minimum_required(VERSION 2.8.3)
project(pein_srvs)

find_package(catkin REQUIRED COMPONENTS
    pein_msgs
    std_msgs
    message_generation
)

################################################
#                                              #
#      ROS MESSAGES, SERVICES AND ACTIONS      #
#                                              #
################################################

# Generate services in the 'srv' folder
add_service_files(
    FILES
    Threshold.srv
    StartStopWithROIArray.srv
    StartStop.srv
    StartStopWithROI.srv
    SetObjects.srv
    TuningMode.srv
    FindObjInRoi.srv
)

generate_messages(
    DEPENDENCIES
        pein_msgs
        std_msgs
)

################################################
#                                              #
#       CATKIN SPECIFIC CONFIGURATION          #
#                                              #
################################################

catkin_package(
    CATKIN_DEPENDS
        pein_msgs
        std_msgs
        message_runtime
)
