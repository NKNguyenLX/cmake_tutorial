cmake_minimum_required(VERSION 2.8.9)
project(directory_test)

#Bring the header, such as Student.h into the project
include_directories(include)

# Can manuaallu add the sources using the set command as follows:
#set(SOURCE src/mainapp.cpp src/ Student.cpp)

# However, the flie(GLOB...) allows for wildcard additions:
file(GLOB SOURCES "src/*.cpp")

add_executable(testStudent ${SOURCES})

# - The include_directories() function is used to bring the header files into
# the build environment.
# The set(SOURCES … ) function can be used to set a variable (SOURCES) that 
# contains the name values of all of the source files (.cpp) in the project. 
# - However, because each source file must be added manually the next line is 
# used in its place, and this line is commented out.
# - The file() command is used to add the source files to the project. 
# GLOB (or GLOB_RECURSE) is used to create a list of all of the files that 
# meet the globbing expression (i.e., “src/*.cpp“) and add them to a variable 
# SOURCES.
# - The add_executable() function uses the SOURCES variable, rather than an 
# explicit reference to each source file, in order to build the testStudent 
# executable program.