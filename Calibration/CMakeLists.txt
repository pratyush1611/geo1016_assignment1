cmake_minimum_required(VERSION 3.1)

get_filename_component(PROJECT_NAME ${CMAKE_CURRENT_SOURCE_DIR} NAME)
project(${PROJECT_NAME})


add_executable(${PROJECT_NAME}
        main.cpp
        camera_calibration.h
        camera_calibration.cpp
        camera_calibration_method.cpp
        matrix.h
        matrix_algo.h
        matrix_algo.cpp
        )

set_target_properties(${PROJECT_NAME} PROPERTIES FOLDER "Calibration")

target_include_directories(${PROJECT_NAME} PRIVATE ${EASY3D_INCLUDE_DIR})

target_compile_definitions(${PROJECT_NAME} PRIVATE GLEW_STATIC)

target_link_libraries(${PROJECT_NAME} core viewer)

