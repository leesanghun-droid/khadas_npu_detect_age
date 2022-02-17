
CMAKE_MINIMUM_REQUIRED(VERSION 3.2)
PROJECT( TEST_PROGRAM)
add_compile_options()

set(lib_gender /home/khadas/khadas_npu_detect_age/detect_age )

ADD_EXECUTABLE( main main.c )#camerastreamer.cc
FIND_PACKAGE( OpenCV REQUIRED )
TARGET_LINK_LIBRARIES   ( main ${OpenCV_LIBS} )
include_directories     (
                                ${lib_gender}/include
                        )
TARGET_LINK_LIBRARIES   (       
                                main  
                                ${lib_gender}/bin_r/libnn_age.so
                                -lovxlib
                        )




