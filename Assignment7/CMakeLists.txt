cmake_minimum_required(VERSION 3.10)
project(RayTracing3)

if (MSVC)
    include(D:/Astudy/AGames/vcpkg/scripts/buildsystems/vcpkg.cmake)
endif ()

set(CMAKE_CXX_STANDARD 17)

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
add_executable(RayTracing3 main.cpp Object.hpp Vector.cpp Vector.hpp Sphere.hpp global.hpp Triangle.hpp Scene.cpp
        Scene.hpp Light.hpp AreaLight.hpp BVH.cpp BVH.hpp Bounds3.hpp Ray.hpp Material.hpp Intersection.hpp
        Renderer.cpp Renderer.hpp)
target_link_libraries(RayTracing3 ${OpenCV_LIBS})
file(COPY ${PROJECT_SOURCE_DIR}/models/ DESTINATION ${PROJECT_BINARY_DIR}/../models/)