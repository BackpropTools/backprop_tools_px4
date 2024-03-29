# BackpropTools: PX4 Module

This example aims at the `Pixracer Pro` which is a `Pixhawk 6C` compliant hardware implementation.

Using the following commit of the PX4 firmware: `7f251d093568179209fa724d155ef0301c3657cf`

Optional: Disable CBRK_BUZZER (INT32)

Add `CONFIG_MODULES_BACKPROP_TOOLS_BENCHMARK=y` in the boards `px4config.default`

Main CMakeList:
- Move the loading of external modules to after then "include(px4_add_library)"
- Change to c++17 in the main

Build with (after changing the path to wherever this repository is located)::
```
make mro_pixracerpro_default EXTERNAL_MODULES_LOCATION=/path/to/this/repository/external_modules
```
Flash with:
```
make mro_pixracerpro_default upload
```


Usage:
- Go into the QGroundControl console
- Start module: `backprop_tools_benchmark start`
- Watch printed output: `dmesg`
