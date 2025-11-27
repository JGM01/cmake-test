# Minimal CMake Project

```bash
# 1. Configure (creates build/ folder automatically)
cmake --preset default

# 2. Build Debug
cmake --build --preset debug

# 3. Run the app
./build/Debug/myapp          # Linux/macOS
./build/Debug/myapp.exe      # Windows

# 4. Run tests
ctest --preset default       # uses Debug by default

# or explicitly:
ctest --preset default -C Release
```

