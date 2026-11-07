cmake_minimum_required(VERSION 3.16)
project(AIOneMeta VERSION 0.1 LANGUAGES CXX C)

set(AIONEMETAPROJECT_MODULES
    "AIOne"
    "AIOneCLI"
    "AIOneJS"
    "AIOneQT"
    "AIOneRS"
    "AIOneServer"
    "AIOneSvelte"
    "AIOneWeb"
    "AIOneWin"
    "AIOneWX"
)

foreach(DIR IN LISTS AIONEMETAPROJECT_MODULES)
    if(EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/${DIR}/CMakeLists.txt")
        add_subdirectory("${DIR}")
    else()
        message(STATUS "Skipping ${DIR} - missing CMakeLists.txt")
    endif()
endforeach()