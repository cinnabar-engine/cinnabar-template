set(NAME demo)

file(GLOB_RECURSE SRC
	"*.cpp"
	"*.c"
)

add_executable(${NAME}
	WIN32
	${SRC}
)


set_target_properties(
	${NAME} PROPERTIES
	VS_DEBUGGER_WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}/res"
)