/*
* use following sniffet in CMakeLists.txt file and use command in build folder : cmake ..
* then use make command
* and then execute
*/

cmake_minimum_required(VERSION 2.8.9)
project(face_recognition)
find_package(OpenBR REQUIRED)
find_package( OpenCV REQUIRED )
find_package(Qt5Widgets REQUIRED)
find_package(Qt5Core REQUIRED)
find_package (Threads REQUIRED)

include_directories( ${OpenCV_INCLUDE_DIRS} )
#find_path(OPENBR_DIR include/openbr/openbr.h)
#link_directories(${OPENBR_DIR}/lib)
#set(OPENBR_LIBS "openbr")
include_directories(${OPENBR_DIR}/include)
add_executable( face_recognition face_recognition.cpp )
target_link_libraries(face_recognition ${OPENBR_LIBS} Qt5::Widgets Qt5::Core ${OpenCV_LIBS})
