cmake_minimum_required(VERSION 3.0.2)
project(px4_code2_msgs)

## Compile as C++11, supported in ROS Kinetic and newer
 add_compile_options(-std=c++11)

## ROS
find_package(catkin REQUIRED COMPONENTS
        mavros_msgs roscpp geometry_msgs message_generation tf nav_msgs) 






#########################
##       MESSAGE       ##
#########################
add_message_files(
        FILES
        Phase.msg
)

##########################
##       SERVICE        ##
##########################
 add_service_files(
   FILES
   Takeoff.srv Lock.srv Land.srv UploadTrajectory.srv
 )

generate_messages(
        DEPENDENCIES
        std_msgs  # Or other packages containing msgs
        mavros_msgs
        nav_msgs
        )


catkin_package(

)

