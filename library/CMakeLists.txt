cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_VERBOSE_MAKEFILE on)
set(CMAKE_ANDROID_STL_TYPE ${CMAKE_ANDROID_STL_TYPE} stlport_static)

set(JNI_DIR src/main/jni)
aux_source_directory(${JNI_DIR} JNI_SRC_LIST)

add_library(gpuimage-library
            SHARED
            ${JNI_SRC_LIST})

set(LIBS)
list(APPEND LIBS
	jnigraphics
	log
)

target_link_libraries(gpuimage-library ${LIBS})