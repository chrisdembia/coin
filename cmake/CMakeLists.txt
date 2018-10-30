include(CMakePackageConfigHelpers)

configure_package_config_file(
    Ipopt-config.cmake.in
    "${CMAKE_CURRENT_BINARY_DIR}/Ipopt-config-to-install.cmake"
    INSTALL_DESTINATION "${IPOPT_INSTALL_CMAKEDIR}"
    PATH_VARS
        CMAKE_INSTALL_PREFIX
        CMAKE_INSTALL_INCLUDEDIR
        CMAKE_INSTALL_LIBDIR
        IPOPT_INSTALL_CMAKEDIR
    )

# write_basic_config_version_file(
#     "${CMAKE_CURRENT_BINARY_DIR}/Ipopt-config-version.cmake"
#     VERSION "${PACKAGE_VERSION}"
#     COMPATIBILITY SameMajorVersion)

install(FILES "${CMAKE_CURRENT_BINARY_DIR}/Ipopt-config-to-install.cmake"
    DESTINATION "${IPOPT_INSTALL_CMAKEDIR}"
    RENAME Ipopt-config.cmake
    )

# install(
#     FILES
#         "${CMAKE_CURRENT_BINARY_DIR}/Ipopt-config-version.cmake"
#     DESTINATION
#         "${IPOPT_INSTALL_CMAKEDIR}"
#         )

install(EXPORT Ipopt-targets DESTINATION "${IPOPT_INSTALL_CMAKEDIR}")
