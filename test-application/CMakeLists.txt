add_executable(test-application
	test-application.cpp)


target_link_libraries(test-application
PRIVATE 
	test-library
)

target_include_directories(test-application
PRIVATE
	${CMAKE_SOURCE_DIR}/test-library
)

add_custom_command(TARGET test-application POST_BUILD
  COMMAND ${CMAKE_COMMAND} -E copy $<TARGET_RUNTIME_DLLS:test-application> $<TARGET_FILE_DIR:test-application>
  COMMAND_EXPAND_LISTS
)