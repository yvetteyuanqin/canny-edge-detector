# Canny Edge Dectector
Canny edge detector written in CUDA C++.

# Dependencies
- CUDA GPGPU framework
- Magick++ image library

## Magick++ Installation
```
./third_party/install_magick++.sh
source ./third_party/magick.env
```

# Compilation
Binaries will be located in the bin/ directory.

Ensure all dependencies have installed successfully, then run:
```
make -j4
```

# Execution
The edge detector supports serial execution on a host CPU, or parallel execution on an NVIDIA GPU.
For command line argument specifics, use the --help option on the generated binary.

To run with default arguments:
```
make run
```

If you plan to run the binary directly (i.e. not using the makefile), ensure you source magick.env:
```
source third_party/magick.env
```

# Debug
To debug, you'll need to compile with the debug option and run manually.
```
# source environment for manual cmd line execution
source third_party/magick.env

# compile with debug symbols and statements
make DEBUG=1 -j4

# run GNU Debugger
gdb ./bin/edge_detect

# once in the gdb terminal, set breakpoints, arguments, etc.
> set args <cmd line args>
> b <file.extension>:<line number> # set break point
> run # run program until breakpoint
> n # execute next line
> step # step down into next line (inside functions, etc.)
```
