set(NAME executable-example)

file(GLOB_RECURSE SRC
	"*.cpp"
	"*.c"
)

add_executable(${NAME}
	WIN32
	${SRC}
)

target_link_libraries(${NAME}
	${CE_LIBS}
	library-example
)

add_custom_command(TARGET ${NAME}
	POST_BUILD
	COMMAND ${CMAKE_COMMAND} -E create_symlink
		${PROJECT_SOURCE_DIR}/resources/${NAME}
		${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/resources
)