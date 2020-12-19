add_library(cluster cluster.cpp)

target_include_directories(cluster PUBLIC include)
target_link_libraries(cluster render)
