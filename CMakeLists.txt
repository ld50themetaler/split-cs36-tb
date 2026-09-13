# Copyright (c) 2024 The ZMK Contributors
# SPDX-License-Identifier: MIT

zephyr_library()

zephyr_include_directories(include)
zephyr_include_directories(${ZEPHYR_BASE}/../zmk/app/include)

if(CONFIG_SPLIT_CS36_TB_TRACKBALL)
    zephyr_library_sources(drivers/trackball/trackball_control.c)
endif()

zephyr_library_sources(drivers/trackball/behavior_trackball.c)

if(CONFIG_PAW3222)
    zephyr_library_sources(drivers/sensor/paw3222/paw3222.c)
endif()
