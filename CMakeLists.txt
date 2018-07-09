cmake_minimum_required (VERSION 3.11)
project(mdio_analyzer)

# custom CMake Modules are located in the cmake directory.
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ExternalAnalyzerSDK)

set(SOURCES 
src/MDIOAnalyzer.cpp
src/MDIOAnalyzer.h
src/MDIOAnalyzerResults.cpp
src/MDIOAnalyzerResults.h
src/MDIOAnalyzerSettings.cpp
src/MDIOAnalyzerSettings.h
src/MDIOSimulationDataGenerator.cpp
src/MDIOSimulationDataGenerator.h
)

add_library(mdio_analyzer SHARED ${SOURCES})
target_link_libraries(mdio_analyzer PRIVATE Saleae::AnalyzerSDK)

if(MSVC)
    install(TARGETS mdio_analyzer RUNTIME DESTINATION ".")
else()
    install(TARGETS mdio_analyzer LIBRARY DESTINATION ".")
endif()

set_post_build_destination(mdio_analyzer)
