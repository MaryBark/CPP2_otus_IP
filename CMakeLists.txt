cmake_minimum_required(VERSION 3.2)

project(ip_filrt_otus2 VERSION 0.0.${PATCH_VERSION})

configure_file(version.h.in version.h)

add_executable(ip_filrt_otus2 main.cpp ip_filtr_lib.h ip_filtr_lib.cpp auxiliary.h auxiliary.cpp)

#set_target_properties(ip_filrt_otus2 PROPERTIES
#        CXX_STANDARD 17
#        CXX_STANDARD_REQUIRED ON
#        COMPILE_OPTIONS "-Wpedantic;-Wall;-Wextra"
#        )


set_target_properties(ip_filrt_otus2 PROPERTIES
        COMPILE_OPTIONS -Wpedantic -Wall -Wextra
        CMAKE_CXX_STANDARD 17
        CMAKE_CXX_STANDARD_REQUIRED ON
)

install(TARGETS ip_filrt_otus2 RUNTIME DESTINATION bin)

set(CPACK_GENERATOR DEB)

set(CPACK_PACKAGE_VERSION_MAJOR "${PROJECT_VERSION_MAJOR}")
set(CPACK_PACKAGE_VERSION_MINOR "${PROJECT_VERSION_MINOR}")
set(CPACK_PACKAGE_VERSION_PATCH "${PROJECT_VERSION_PATCH}")

set(CPACK_PACKAGE_CONTACT Alttaira@yandex.ru)

include(CPack)
