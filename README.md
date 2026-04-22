# Cub3D_tester

## Description

These tests are created with certain textures and maps that you can find in the repository. The name of the test explains the test; if you are in need of more specific details, then check the args/map tested in the specific test.

All tests are tested with `valgrind` on leaks, and they check the `stderr` to have `Error\n` as the first thing, since that is what is required by the subject of the project.

## Getting Started / Instructions

First, you need to install the dependencies like `criterion`. Depending on your system:
- **Ubuntu/Debian**: `sudo apt install libcriterion-dev`
- **macOS**: `brew install criterion`
(Check for any extra dependencies as needed for your specific platform).

You can modify the name of the executable in `tests/tester.c` at `#define PROG "./cub3D"` with the correct path/executable name (in case you want to test the bonus, e.g., `./cub3D_bonus`).

The exit code of your program in case of errors has to be adjusted in `#define EXIT_CODE`. By default, it is `1`.

> **Note**: If your exit code is different from the defined `EXIT_CODE`, the test will print a message that "valgrind detected leaks". This is because it expects the exit code of the program to match the `EXIT_CODE` (in case valgrind doesn't find errors). If valgrind *does* find errors, it will return `42`, so that will trigger the assert function to fail and write the "valgrind detected leaks" message.
