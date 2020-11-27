cmake_minimum_required(VERSION 3.3)

project(PathTracer)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(MxEngine)

set(SOURCES
    "src/MxApplication.cpp"
)

add_executable(${CMAKE_PROJECT_NAME} ${SOURCES})

target_link_libraries(${CMAKE_PROJECT_NAME} PUBLIC MxEngine)
target_include_directories(${CMAKE_PROJECT_NAME} PUBLIC ${MxEngine_INCLUDE_DIR})

# used to copy shaders and libraries to project build folder
include(${MxEngine_CMAKE_UTILS_DIR}/project_install.cmake)
install_mxengine_project(${CMAKE_PROJECT_NAME})