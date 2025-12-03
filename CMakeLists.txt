set(SDfat ${CMAKE_CURRENT_LIST_DIR})

if(DEFINED ESP_PLATFORM)
    set(COMPONENT_ADD_INCLUDEDIRS
        ${SDfat}/src
    )
    file(GLOB_RECURSE SRCS
        ${SDfat}/src/*.cpp
    )

    set(COMPONENT_SRCS ${SRCS})


    set(COMPONENT_REQUIRES arduino-esp32)


    ### If you use arduino-esp32 components, please activate next comment line.
    # list(APPEND COMPONENT_REQUIRES arduino-esp32)


    message(STATUS "SdFat use components = ${COMPONENT_REQUIRES}")

    register_component()
else()
    message("Error: No platform specified")
endif()
