cmake_minimum_required(VERSION 3.6)
project(JermanEnhance)

find_package(ITK REQUIRED)
include (${ITK_USE_FILE})

# Include project headers
include_directories(./include)

# Define the source files and dependencies for the executable
set(SOURCE_FILES
	JermanEnhance.cpp
	
)

add_executable(JermanEnhance ${SOURCE_FILES})

if (ITK_LIBRARIES)
	target_link_libraries(JermanEnhance ${ITK_LIBRARIES})
	message("Correct version of ITK")
else()
	message("uh oh, didn't link")
	target_link_libraries(JermanEnhance itkHybrid itkWidgets)
endif()

