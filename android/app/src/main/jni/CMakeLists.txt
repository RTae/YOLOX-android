project(yoloXncnn)

cmake_minimum_required(VERSION 3.10)

set(ncnn_DIR ${CMAKE_SOURCE_DIR}/ncnn-20210720-android-vulkan/${ANDROID_ABI}/lib/cmake/ncnn)
find_package(ncnn REQUIRED)

set(OpenCV_DIR ${CMAKE_SOURCE_DIR}/opencv-mobile-4.5.3-android/sdk/native/jni)
find_package(OpenCV REQUIRED core imgproc)

add_library(yoloXncnn SHARED yoloXncnn_jni.cpp)

target_link_libraries(
        yoloXncnn
        ncnn
        jnigraphics
        ${OpenCV_LIBS}
)
