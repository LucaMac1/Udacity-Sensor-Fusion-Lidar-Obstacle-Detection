add_library(process_point_clouds INTERFACE)

target_include_directories(process_point_clouds INTERFACE include)

#target_link_libraries(process_point_clouds ${PCL_LIBRARIES} cluster render)

#target_link_library(another-users-target my-library)
target_link_libraries(process_point_clouds INTERFACE ${PCL_LIBRARIES} cluster render)