CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
PROJECT(assrender)

ADD_SUBDIRECTORY(src)

IF(MINGW)
    SET(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} -static-libgcc -Wl,--add-stdcall-alias")
    SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c99 -Wpedantic")
    SET(CMAKE_SHARED_LINKER_FLAGS_RELEASE "-s")
    SET(CMAKE_C_FLAGS_RELEASE "-O3")
ENDIF()

