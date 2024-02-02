## Author

👋 Hi, I'm Luke!

Welcome to my GitHub repository. I'm passionate about making programming accessible and enjoyable for everyone. Whether you're just starting out or an experienced developer, you'll find valuable insights in my tutorials and courses.

🌟 **Support my work:**
- 🌐 Visit [my website](https://www.lukesdevtutorials.com) for more resources.
- ▶️ Subscribe to [my YouTube channel](https://www.youtube.com/@lukesdevtutorials) for free tutorials and courses.

Your support means the world to me!

## Project Overview

Full Tutorial: https://www.youtube.com/watch?v=zjNg5HdgNO0

Download, build and statically link wxWidgets as the GUI library for your C++ project!

```cmake
cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

project(wx_cmake_fetchcontent_template LANGUAGES CXX)

include(FetchContent)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(wxBUILD_SHARED OFF)

message(STATUS "Fetching wxWidgets...")

FetchContent_Declare(
   wxWidgets
   GIT_REPOSITORY https://github.com/wxWidgets/wxWidgets.git
   GIT_SHALLOW ON
)
FetchContent_MakeAvailable(wxWidgets)

set(SRCS main.cpp)

add_executable(main WIN32 ${SRCS})
target_link_libraries(main PRIVATE wxcore wxnet)
```

## System Requirements

To get started with this project, ensure you have the following tools and libraries:

- **CMake (Version 3.14 or later):** Essential for building and managing the project files.
- **C++ Compiler:** Compatible with Clang, GCC, or MSVC. Choose one based on your development environment.
- **GTK3 Development Libraries (for Linux users):** Necessary for GUI development on Linux platforms.

## Building the Project

# Debug

Follow these steps to build the project:

1. **Create a build directory & configure the build:**
   ```bash
   cmake -S. -Bbuild
   ```

2. **Build the project:**
   ```bash
   cmake --build build -j
   ```

This will create a `build` directory and compile all necessary artifacts there. The main executable will be located in `build/`.

# Release

For release build use `--config Release` on Windows:

```bash
cmake -S. -Bbuild
cmake --build build -j --config Release
```

Artifacts for both configurations will be generated in the `build` directory.

On Mac or Linux you'll need to maintain two build trees:

```bash
cmake -S. -Bbuild -DCMAKE_BUILD_TYPE=Debug
cmake --build build -j
cmake -S. -Bbuild-rel -DCMAKE_BUILD_TYPE=Release
cmake --build build-rel -j
```

## License

MIT License. Can be used in closed-source commercial products.
