if (TARGET "Samples.Utils" AND TARGET "DevIL-lib" AND TARGET "STB-lib" AND TARGET "TinyObj-lib")
	file( GLOB_RECURSE SOURCES "*.h" "*.cpp" "*.frag" "*.vert" "*.comp" )
	add_executable( "Samples.Clouds" ${SOURCES} )
	source_group( TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SOURCES} )
	target_include_directories( "Samples.Clouds" PUBLIC "." )
	target_include_directories( "Samples.Clouds" PUBLIC "../cloud_libs/stb" )
	target_include_directories( "Samples.Clouds" PUBLIC "../cloud_libs/tinyobj" )
	set_property( TARGET "Samples.Clouds" PROPERTY FOLDER "Samples" )
	target_link_libraries( "Samples.Clouds" PUBLIC "Samples.Utils" )
	target_link_libraries( "Samples.Clouds" PUBLIC "STB-lib" )
	target_link_libraries( "Samples.Clouds" PUBLIC "TinyObj-lib" )
	target_compile_definitions( "Samples.Clouds" PUBLIC "FG_DATA_PATH=R\"(${CMAKE_CURRENT_SOURCE_DIR}/)\"" )
endif ()
