# CMakeList.txt : CMake project for FunctionalCpp, include source and define
# project specific logic here.
#

# Add source to this project's executable.
add_executable (FunctionalCpp "FunctionalCpp.cpp" "FunctionalCpp.h")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET FunctionalCpp PROPERTY CXX_STANDARD 20)
endif()

target_include_directories (FunctionalCpp PRIVATE "external/RxCpp/Rx/v2/src")

add_subdirectory ("external/Catch2")

target_link_libraries (FunctionalCpp PRIVATE Catch2::Catch2WithMain)
