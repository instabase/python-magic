load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "rules_foreign_cc",
    sha256 = "476303bd0f1b04cc311fc258f1708a5f6ef82d3091e53fd1977fa20383425a6a",
    strip_prefix = "rules_foreign_cc-0.10.1",
    url = "https://github.com/bazelbuild/rules_foreign_cc/releases/download/0.10.1/rules_foreign_cc-0.10.1.tar.gz",
)

load("@rules_foreign_cc//foreign_cc:repositories.bzl", "rules_foreign_cc_dependencies")

rules_foreign_cc_dependencies()

http_archive(
    name = "libmagic_macos",
    sha256 = "09c588dac9cff4baa054f51a36141793bcf64926edc909594111ceae60fce4ee",
    strip_prefix = "file-5.31",
    urls = [
        "https://astron.com/pub/file/file-5.31.tar.gz",
    ],
    patch_cmds = [
        "./configure",
        "make",
        "make install",
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
