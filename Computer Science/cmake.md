CMake is an open-source, cross-platform family of tools designed to build, test, and package software using compiler-independent configuration files. It is basically the de facto build tool for [[C++]].
* CMake is a meta-build system. It does not build the project directly; instead, it generates the native build scripts, like Ninja files, [[make|Makefiles]], or Visual Studio solutions)

# Commands
* **`cmake -S . -B build`**: The **Configure** step. `-S .` points to the source code; `-B build` creates a directory where the generated build files will live.
* **`cmake --build build`**: The **Build** step. This tells CMake to run the underlying build tool (like `make` or `msbuild`) to actually compile the code.
* **`cmake --install build`**: Moves the compiled binaries and headers to their final system location (e.g., `/usr/local/bin`).