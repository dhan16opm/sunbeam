pybind11_add_module(libsunbeam sunbeam.cpp
                               eclipse_state.cpp
                               deck_keyword.cpp
                               deck.cpp
                               well.cpp
                               sunbeam_state.cpp
                               schedule.cpp
                               connection.cpp
                               eclipse_config.cpp
                               table_manager.cpp
                               eclipse_grid.cpp
                               group.cpp
                               group_tree.cpp
                               eclipse_3d_properties.cpp
                               parser.cpp)

set_target_properties( libsunbeam PROPERTIES LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/python/sunbeam )
include_directories( ${opm-common_INCLUDE_DIRS} )
message(${opm-common_LIBRARIES})
target_link_libraries( libsunbeam PRIVATE ${opm-common_LIBRARIES} )
install(TARGETS libsunbeam DESTINATION ${PYTHON_INSTALL_PREFIX}/sunbeam)
