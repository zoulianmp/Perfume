include(ExternalProject)

if (NOT DEPS_LOCATION)
    set(DEPS_LOCATION "${CMAKE_BINARY_DIR}/deps")
endif()

ExternalProject_Add(log4cplus
    GIT_REPOSITORY https://github.com/log4cplus/log4cplus.git
    GIT_TAG "1.2.x"
    CMAKE_ARGS -DBUILD_SHARED_LIBS=OFF -DCMAKE_INSTALL_PREFIX=${DEPS_LOCATION} 
               -DUNICODE=OFF -DLOG4CPLUS_BUILD_LOGGINGSERVER=OFF
               -DLOG4CPLUS_BUILD_TESTING=OFF -DCMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE}
    PREFIX "${DEPS_LOCATION}"
    INSTALL_DIR "${DEPS_LOCATION}"
)
