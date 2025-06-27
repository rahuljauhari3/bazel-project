# Bazel C++ Project Plan

## 1. Project Structure

```
bazel-project/
│
├── WORKSPACE
├── BUILD
├── workspace.bzl
├── src/
│   ├── hello.cc
│   ├── hello.h
│   └── main.cc
├── python/
│   ├── __init__.py
│   └── hello_wrapper.py
├── wheel/
│   └── BUILD
└── README.md
```

## 2. Steps

a. Create a simple C++ library and binary
- `src/hello.h` and `src/hello.cc`: Simple C++ function (e.g., say_hello).
- `src/main.cc`: Uses the library and prints output.
- `BUILD`: Use `cc_library` for the library and `cc_binary` for the executable.

b. Create a shared library (.so)
- Modify `cc_library` to build a shared library (`linkstatic = 0`).
- Output: `libhello.so`.

c. Create a Python wrapper
- `python/hello_wrapper.py`: Uses `ctypes` or `pybind11` to load the `.so`.
- `BUILD`: Use `py_library` or `py_binary` if needed.

d. Package as a Python wheel
- Use Bazel rules (e.g., rules_python, rules_pkg) to create a `.whl` file.
- `wheel/BUILD`: Define a target to build the wheel, including the `.so` and Python files.

e. Custom workspace.bzl
- Add a simple macro or repository rule in `workspace.bzl` and load it in `WORKSPACE` to demonstrate custom Bazel extension.

f. Documentation
- Update `README.md` with build and usage instructions.

## 3. Key Bazel Files

- `WORKSPACE`: Declares the workspace and loads custom rules.
- `workspace.bzl`: Contains a simple macro or repository rule.
- `BUILD`: Defines `cc_library`, `cc_binary`, and Python targets.
- `wheel/BUILD`: Defines the wheel packaging target.
