set (BOOST_ROOT "C:/Users/jeong/libraries/boost_1_81_0")
set (BOOST_LIBRARY_DIR  "C:/Users/jeong/libraries/boost_1_81_0/lib")

set (CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

add_library(test-library SHARED # SHARED(Dynamic) / STATIC 
	test-library.cpp test-library.h)

find_package(Boost REQUIRED)

include_directories(${Boost_INCLUDE_DIR})

target_link_libraries(test-library ${Boost_SYSTEM_LIBRARY})
