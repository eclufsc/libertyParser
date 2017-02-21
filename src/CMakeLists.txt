# LIBRARY
file(GLOB LIB_SOURCES "*.c")
list(REMOVE_ITEM LIB_SOURCES "main.c")
message(${LIB_SOURCES})
file(GLOB LIB_HEADERS "../include/*.h")

add_library(si2dr_liberty ${LIB_SOURCES} ${LIB_HEADERS})
target_include_directories(si2dr_liberty PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/../include)

# TEST
add_executable(si2dr_liberty_parser main.c)
target_link_libraries(si2dr_liberty_parser si2dr_liberty)
target_include_directories(si2dr_liberty_parser PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/../include)
