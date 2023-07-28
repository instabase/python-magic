py_library(
    name = "loader",
    srcs = ["loader.py", "__init__.py"],
    imports = [".."],
    data = [
        "@libmagic//:libmagic",
    ],
    visibility = ["//visibility:public"],
)

py_library(
    name = "compat",
    srcs = ["compat.py"],
    imports = [".."],
    data = [
        ":loader",
    ],
    visibility = ["//visibility:public"],
)