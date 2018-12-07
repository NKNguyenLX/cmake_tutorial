cmake_minimum_required(VERSION 2.8.9)
project (TestLibrary)

# For the shared library:
set(PROJECT_LINK_LIBS libtestStudent.so)
link_directories(/usr/lib)

# For the static library:
# set(PROJECT_LINK_LIBS libtestStudent.a)
# link_directories(~/Works/git/cmake_tutorial/tut_4_building_a_static_library/build)

include_directories(/home/nknight/Works/git/cmake_tutorial/tut_4_building_a_static_library/include)

add_executable(libtest libtest.cpp)
target_link_libraries(libtest ${PROJECT_LINK_LIBS})
