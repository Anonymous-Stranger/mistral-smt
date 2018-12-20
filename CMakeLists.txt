# (c) Isil Dillig (isil@cs.stanford.edu), Thomas Dillig (tdillig@cs.stanford.edu)

project(mistral)

set(CMAKE_CXX_COMPILER "g++")
set(CMAKE_C_COMPILER "gcc")

set (CMAKE_BUILD_TYPE Debug)

set(CMAKE_CXX_FLAGS "-std=c++0x -O2 -mtune=native -march=native -ftree-vectorize -funroll-loops -fstrict-aliasing  -fno-stack-protector -ffast-math -mfpmath=sse -msse3 -Wall -fmessage-length=0 -g ")
set(CMAKE_CXX_FLAGS_DEBUG "-std=c++0x -O2 -mtune=native -march=native -ftree-vectorize -funroll-loops -fstrict-aliasing  -fno-stack-protector -ffast-math -mfpmath=sse -msse3 -Wall -fmessage-length=0 -g ")

#set(CMAKE_CXX_FLAGS "-std=c++0x -g")
#set(CMAKE_CXX_FLAGS_DEBUG "-std=c++0x -g")



file(GLOB MY_SRC "*.cpp" "cnode/*.cpp" "elimination/*.cpp" "numeric-lib/*.cpp" "sat-solver/*.cpp" "solver/*.cpp" "term/*.cpp")

set(MISTRAL_INCLUDE_DIRS
    ${PROJECT_SOURCE_DIR}
    ${PROJECT_SOURCE_DIR}/cnode
    ${PROJECT_SOURCE_DIR}/numeric-lib
    ${PROJECT_SOURCE_DIR}/elimination
    ${PROJECT_SOURCE_DIR}/sat-solver
    ${PROJECT_SOURCE_DIR}/solver
    ${PROJECT_SOURCE_DIR}/term
    ${PROJECT_SOURCE_DIR}/parser
    ${PROJECT_SOURCE_DIR}/smtparser
  CACHE INTERNAL "${PROJECT_NAME}: Include Directories" FORCE)

include_directories(${MISTRAL_INCLUDE_DIRS})
add_library(mistral ${MY_SRC})
TARGET_LINK_LIBRARIES(mistral parser smtparser)

add_subdirectory(parser)
add_subdirectory(smtparser)
add_subdirectory(ui)
