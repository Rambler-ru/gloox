cmake_minimum_required(VERSION 2.6.0 FATAL_ERROR)
file( GLOB gloox_SRCS *.cpp )

SET(LIBS ssl z)
add_library( gloox SHARED ${gloox_SRCS} )
target_link_libraries( gloox ${LIBS} )
set_target_properties( gloox PROPERTIES SOVERSION 9 )
include_directories( ${gloox_SOURCE_DIR})
add_definitions( -DGLOOX_EXPORTS -DDLL_EXPORT )
