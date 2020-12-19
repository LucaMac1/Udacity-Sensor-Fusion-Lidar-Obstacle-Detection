add_library(render render.cpp)

target_include_directories(render PUBLIC include)
target_link_libraries(render ${PCL_LIBRARIES})

# PCL library
#target_include_directories(${TARGET_NAME} PRIVATE ${PCL_INCLUDE_DIRS})
#target_link_libraries(${TARGET_NAME} ${PCL_LIBRARIES} sensors render process_point_clouds)