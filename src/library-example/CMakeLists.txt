set(NAME library-example)
set(BUILD_SHARED_LIBS TRUE)

file(GLOB_RECURSE SRC
	"*.cpp"
	"*.c"
)

add_library(${NAME}
	${SRC}
)

target_link_libraries(${NAME}
	${CE_LIBS}
)