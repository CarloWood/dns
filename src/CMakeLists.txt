cmake_minimum_required( VERSION 3.0 )

project( dns
         DESCRIPTION "A non-blocking DNS resolver library in a single .c file"
         LANGUAGES C
)

#==============================================================================
# BUILD OBJECT LIBRARY
#

# This project is an OBJECT-library, used by other git submodules and the main project.
add_library( dns_ObjLib OBJECT )

# Set SOURCE_DIR to the current directory.
set_property(
    TARGET     dns_ObjLib
    PROPERTY   SOURCE_DIR       "${CMAKE_CURRENT_SOURCE_DIR}"
)

# The list of source files.
target_sources( dns_ObjLib
    PRIVATE
        "dns.c"

        "dns.h"
)

# Requires -std=gnu99
set_property( TARGET dns_ObjLib
              PROPERTY C_STANDARD 99
)

target_compile_options( dns_ObjLib
    PRIVATE -fstack-protector -Wall -Wextra
)

# Create an ALIAS target.
add_library( dns::dns ALIAS dns_ObjLib )
