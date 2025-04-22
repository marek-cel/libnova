set(TARGET_NAME libnova-libnova)

################################################################################

set(HEADERS
    aberration.h
    airmass.h
    angular_separation.h
    apparent_position.h
    asteroid.h
    comet.h
    confdefs.h
    constellation.h
    dynamical_time.h
    earth.h
    elliptic_motion.h
    heliocentric_time.h
    hyperbolic_motion.h
    julian_day.h
    jupiter.h
    libnova.h
    ln_types.h
    lunar.h
    mars.h
    mercury.h
    neptune.h
    nutation.h
    parabolic_motion.h
    parallax.h
    pluto.h
    precession.h
    proper_motion.h
    refraction.h
    rise_set.h
    saturn.h
    sidereal_time.h
    solar.h
    transform.h
    uranus.h
    utility.h
    venus.h
    vsop87.h
)

################################################################################

add_library(${TARGET_NAME} INTERFACE)

################################################################################

set_target_properties(${TARGET_NAME} PROPERTIES
    PUBLIC_HEADER "${HEADERS}"
)

install(TARGETS ${TARGET_NAME}
    PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/libnova
)
