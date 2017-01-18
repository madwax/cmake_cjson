project(cJSON C)

set( cJSON_INCLUDE_DIR ${cJSON_SOURCE_DIR}/include )

set( cJSON_SOURCES ${cJSON_SOURCE_DIR}/src/cJSON.c )

add_library( cJSON STATIC ${cJSON_SOURCES} )

set_target_properties( cJSON PROPERTIES ARCHIVE_OUTPUT_NAME "cJSON" )

target_include_directories( cJSON PRIVATE ${cJSON_INCLUDE_DIR} )
target_include_directories( cJSON INTERFACE $<BUILD_INTERFACE:${cJSON_INCLUDE_DIR}> )