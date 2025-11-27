# Minimal CMake Project

Configure (creates build/ folder automatically)
`cmake --preset default`

Build Debug
`cmake --build --preset debug`

Run the app (use .exe on Windows)
`./build/Debug/myapp`
`./build/Debug/myapp.exe`

Run tests (defaults to Debug)
`ctest --preset default`
