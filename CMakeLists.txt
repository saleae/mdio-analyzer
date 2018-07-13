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

add_analyzer_plugin(mdio_analyzer SOURCES ${SOURCES})
