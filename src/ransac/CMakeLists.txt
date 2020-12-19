add_library(ransac ransac2d.cpp)

target_link_libraries(ransac PUBLIC ${PCL_LIBRARIES} process_point_clouds render)