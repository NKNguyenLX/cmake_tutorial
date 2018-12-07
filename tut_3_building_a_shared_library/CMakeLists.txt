cmake_minimum_required(VERSION 2.8.9)
project(directory_test)
set(CMAKE_BUILD_TYPE Release)

#Bring the headers, such as Student.h into the project
include_directories(include)

#However, the file(GLOB...) allows for wildcard additions:
file(GLOB SOURCES "src/*.cpp")

#Generate the shared library from the sources
add_library(testStudent SHARED ${SOURCES})

# Set the location for libreary installation -- i.e.,/usr/lib inthis 
# case not really necessary in this example. Use "sudo make install"
# to apply
install(TARGETS testStudent DESTINATION /usr/lib)

# - The set(CMAKE_BUILD_TYPE Release) function is used to set the build
# type to be a release build.
# - Instead of the add_executable() function that is used in previous 
# examples, this example uses the add_library() function. The library 
# is built as a shared library using the SHARED flag (other options 
# are: STATIC or MODULE), and the testStudent name is used as 
# the name of the shared library.
# - The last line uses the install() function to define an installation 
# location for the library (in this case it is /usr/lib). Deployment 
# is invoked using a call to sudo make install in this case.

# The libtestStudent.so library can be installed system wide using:
# $ sudo make install
# Check
# $ ls -l /usr/lib|grep libtest*

# - You will also find a file in the build directory, called 
# install_manifest.txt that describes the locations at which the 
# make install command applied changes.

