SET(CELLBIN_SRCS
	cellapp.cpp  
	main.cpp
)


include_directories(
	./
	../common/
	../base/
)

add_executable(cellapp
    ${CELLBIN_SRCS}
)

TARGET_LINK_LIBRARIES(cellapp "common")
TARGET_LINK_LIBRARIES(cellapp "ssl")
TARGET_LINK_LIBRARIES(cellapp "crypto")
TARGET_LINK_LIBRARIES(cellapp "lua.5.2.4")
TARGET_LINK_LIBRARIES(cellapp "boost_regex")
TARGET_LINK_LIBRARIES(cellapp "mysqlclient")


set_target_properties(cellapp PROPERTIES
    OUTPUT_NAME "cellapp"
    CLEAN_DIRECT_OUTPUT 1
    VERSION ${DARKSERVER_VERSION}
)

set_target_properties(cellapp PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)
set_target_properties(cellapp PROPERTIES RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_SOURCE_DIR}/bin)
set_target_properties(cellapp PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_SOURCE_DIR}/bin)