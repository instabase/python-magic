load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "libmagic",
    sha256 = "09c588dac9cff4baa054f51a36141793bcf64926edc909594111ceae60fce4ee",
    strip_prefix = "file-5.31",
    urls = [
        "https://astron.com/pub/file/file-5.31.tar.gz",
    ],
    patch_cmds = [
        "./configure",
        "make",
        "make install",
        "cp src/.libs/libmagic.dylib /usr/local/lib/libmagic.dylib",
    ],
    build_file_content = """
cc_library(
    name = 'libmagic',
    srcs = ["src/.libs/libmagic.dylib"],
    includes = ['.'],
    linkstatic = 1,
    visibility = ['//visibility:public'],
)""",
)