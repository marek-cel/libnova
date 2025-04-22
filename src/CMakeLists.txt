set(TARGET_NAME nova)

################################################################################

if(WIN32)
    if(BUILD_SHARED_LIBS)
        add_definitions(-DLIBNOVA_DLL_EXPORTS)
    endif()
endif()

################################################################################

set(SOURCES
    aberration.c
    airmass.c
    angular_separation.c
    apparent_position.c
    asteroid.c
    comet.c
    constellation.c
    dynamical_time.c
    earth.c
    elliptic_motion.c
    heliocentric_time.c
    hyperbolic_motion.c
    julian_day.c
    jupiter.c
    lunar.c
    mars.c
    mercury.c
    misc.c
    neptune.c
    nutation.c
    parabolic_motion.c
    parallax.c
    pluto.c
    precession.c
    proper_motion.c
    refraction.c
    rise_set.c
    saturn.c
    sidereal_time.c
    solar.c
    transform.c
    uranus.c
    utility.c
    venus.c
    vsop87.c
)

################################################################################

add_subdirectory(elp)
add_subdirectory(libnova)

################################################################################

add_library(${TARGET_NAME} ${SOURCES}
    $<TARGET_OBJECTS:libnova-elp>
)

################################################################################

# set_target_properties(${TARGET_NAME} PROPERTIES
#     VERSION ${MCSIM_VERSION_STRING}
#     SOVERSION ${MCSIM_VERSION_MAJOR}
#     PUBLIC_HEADER "${HEADERS}"
# )

# install(TARGETS ${TARGET_NAME}
#     LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
#     PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/mcsim
# )

################################################################################

target_link_libraries(${TARGET_NAME} ${LIBS})
