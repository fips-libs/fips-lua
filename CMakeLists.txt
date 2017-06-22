if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    fips_setup(PROJECT lua)
endif()

fips_begin_lib(lua)
    fips_src(lua NO_RECURSE)
fips_end_lib()

if (NOT FIPS_IMPORT)
    fips_finish()
endif()

