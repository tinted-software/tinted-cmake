cmake_minimum_required(VERSION 3.29)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_DISABLE_SOURCE_CHANGES ON)
set(CMAKE_DISABLE_IN_SOURCE_BUILD ON)

set(CMAKE_CXX_VISIBILITY_PRESET hidden)
set(CMAKE_VISIBILITY_INLINES_HIDDEN 1)

project(art LANGUAGES CXX)

if (NOT ANDROID_SOURCE_DIR)
	message(FATAL_ERROR "ANDROID_SOURCE_DIR is not set")
endif()

set(ART_SOURCE_DIR ${ANDROID_SOURCE_DIR}/art CACHE PATH "Path to art source directory")
set(LIBBASE_SOURCE_DIR ${ANDROID_SOURCE_DIR}/android_system_libbase CACHE PATH "Path to libbase source directory")
set(LIBLOG_SOURCE_DIR ${ANDROID_SOURCE_DIR}/android_system_logging/liblog CACHE PATH "Path to liblog source directory")
set(LIBCUTILS_SOURCE_DIR ${ANDROID_SOURCE_DIR}/android_system_core/libcutils CACHE PATH "Path to libcutils source directory")
set(LIBUTILS_SOURCE_DIR ${ANDROID_SOURCE_DIR}/android_system_core/libutils CACHE PATH "Path to libutils source directory")
set(LIBSYSTEM_SOURCE_DIR ${ANDROID_SOURCE_DIR}/android_system_core/libsystem CACHE PATH "Path to libsystem source directory")

include(cmake/android_base.cmake)
include(cmake/android_art_base.cmake)
