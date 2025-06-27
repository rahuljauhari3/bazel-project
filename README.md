# Bazel C++ Example Project

This project demonstrates how to use Bazel to build a simple C++ library and binary. The project structure and build steps are designed to showcase Bazel's capabilities for C++ builds.

## Build the C++ library and binary

This step builds the core C++ components:
- `//src:hello` is a C++ library target defined in `src/hello.cc` and `src/hello.h`. It provides a simple function (e.g., `say_hello`).
- `//src:hello_app` is a C++ binary target defined in `src/main.cc` that links against the `hello` library and prints output to the console.

Run the following commands to build both:

```
bazel build //src:hello
bazel build //src:hello_app
```

## Run the C++ binary

After building, you can run the C++ executable directly. This will print output from the C++ code:

```
./bazel-bin/src/hello_app
```

## List C++ Libraries and Binaries with Bazel Query

Bazel provides a powerful query language to inspect your build targets. To list all C++ libraries and binaries defined in your workspace, use:

```
bazel query 'kind("cc_(library|binary)", //...)'
```
This command helps you verify which C++ targets are available and can be useful for debugging or understanding the project structure.
