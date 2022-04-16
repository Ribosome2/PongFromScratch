cmake_minimum_required(VERSION 3.21)
PROJECT(PongFromScratch)

FIND_PACKAGE(Vulkan REQUIRED)
INCLUDE_DIRECTORIES(${VULKAN_SDK}/Include)
INCLUDE_DIRECTORIES(src)

ADD_COMPILE_DEFINITIONS("WINDOWS_BUILD") #use this compile option when building on windows

ADD_EXECUTABLE(${PROJECT_NAME}
        src/platform/win32_platform.cpp
        )

TARGET_LINK_LIBRARIES(${PROJECT_NAME} PRIVATE Vulkan::Vulkan)
