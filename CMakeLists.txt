cmake_minimum_required (VERSION 2.8)
cmake_policy(VERSION 2.8)

project (ShadowVolume)
set(CMAKE_CXX_STANDARD 14)

find_package(GLM REQUIRED)
message(STATUS GLM included at ${GLM_INCLUDE_DIR})
find_package(GLFW3 REQUIRED)
message(STATUS Found GLFW3 in ${GLFW3_INCLUDE_DIR} ${GLFW3_LIBRARY})
set(GLFW3_LIBRARY /usr/local/lib/libglfw.dylib)
include_directories(Include)
add_executable(ShadowVolumeDemo Shader.cpp Shader.h MeshCreator.h MeshCreator.cpp Mesh.h Mesh.cpp main.cpp glad.c Camera.cpp Camera.h)
target_link_libraries(ShadowVolumeDemo ${GLFW3_LIBRARY})