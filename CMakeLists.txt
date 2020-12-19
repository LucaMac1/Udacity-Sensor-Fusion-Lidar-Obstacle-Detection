set(PROJECT_NAME "lidar_obstacle_detection")
set(TARGET_NAME "lidar-obstacle-detection")
set(DESCRIPTION "A simple 3D highway environment using PCL
                for exploring self-driving car sensors")
set(AUTHOR "Luca Macchiusi <macchiusiluca@gmail.com>")
set(PROJECT_URL "https://github.com/LucaMac1/Udacity-Sensor-Fusion-Lidar-Obstacle-Detection")

#-----------------------------------------------------------------------------------------------#

cmake_minimum_required(VERSION 3.17)
project(${PROJECT_NAME} LANGUAGES CXX)

# Find Packages
find_package(PCL 1.11 REQUIRED)

# Add target subdirectories.
add_subdirectory(${PROJECT_SOURCE_DIR}/src/cluster)
add_subdirectory(${PROJECT_SOURCE_DIR}/src/process-point-clouds)
add_subdirectory(${PROJECT_SOURCE_DIR}/src/ransac)
add_subdirectory(${PROJECT_SOURCE_DIR}/src/render)
add_subdirectory(${PROJECT_SOURCE_DIR}/src/sensors)

# Define source and header files.
set(SOURCE_FILES
    ${CMAKE_CURRENT_SOURCE_DIR}/environment.cpp
)
set(HEADER_FILES
)

# Create an executable with required definitions and libraries.
add_executable(${TARGET_NAME} ${SOURCE_FILES} ${HEADER_FILES})
set_target_properties(${TARGET_NAME} PROPERTIES CXX_STANDARD 11 CXX_STANDARD_REQUIRED ON)

# PCL library
target_include_directories(${TARGET_NAME} PRIVATE ${PCL_INCLUDE_DIRS})
target_link_libraries(${TARGET_NAME} ${PCL_LIBRARIES} sensors render process_point_clouds)
