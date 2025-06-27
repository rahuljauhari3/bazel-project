cc_library(
    name = "hello",
    srcs = ["hello.cc"],
    hdrs = ["hello.h"],
    visibility = ["//visibility:public"],
    linkstatic = 0,  # Build as shared library
)

cc_binary(
    name = "hello_app",
    srcs = ["main.cc"],
    deps = [":hello"],
) 