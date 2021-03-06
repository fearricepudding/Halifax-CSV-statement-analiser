cmake_minimum_required(VERSION 3.5)

project(FinancialOrganiser LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

include_directories(/usr/include /usr/local/include)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt5 COMPONENTS Widgets REQUIRED)

add_executable(FinancialOrganiser
  ui/mainwindow.ui
  ui/importstatement.ui
  ui/mystatements.ui
  
  src/main.cpp
  src/mainwindow.cpp
  src/CsvParser.cpp
  src/importstatement.cpp
  src/database.cpp
  src/mystatements.cpp
  
  src/mainwindow.h
  src/CsvParser.h
  src/importstatement.h
  src/database.h
  src/mystatements.h
)

target_link_libraries(FinancialOrganiser PRIVATE Qt5::Widgets jsoncpp)
