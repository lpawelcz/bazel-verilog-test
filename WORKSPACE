load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:utils.bzl", "maybe")

maybe(
    git_repository,
    name = "rules_hdl",
    remote = "https://github.com/hdl/bazel_rules_hdl",
    commit = "6689294f2d4f45de02a527d947b4703b4c008b53",
    shallow_since = "1676530055 -0800",
)

load("@rules_hdl//toolchains/cpython:cpython_toolchain.bzl", "register_cpython_repository")

register_cpython_repository()

register_toolchains("@rules_hdl//toolchains/cpython:cpython_toolchain")

maybe(
    http_archive,
    name = "rules_python",
    sha256 = "b6d46438523a3ec0f3cead544190ee13223a52f6a6765a29eae7b7cc24cc83a0",
    url = "https://github.com/bazelbuild/rules_python/releases/download/0.1.0/rules_python-0.1.0.tar.gz",
)


maybe(
    http_archive,
    name = "rules_pkg",
    sha256 = "a89e203d3cf264e564fcb96b6e06dd70bc0557356eb48400ce4b5d97c2c3720d",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_pkg/releases/download/0.5.1/rules_pkg-0.5.1.tar.gz",
        "https://github.com/bazelbuild/rules_pkg/releases/download/0.5.1/rules_pkg-0.5.1.tar.gz",
    ],
)


load("@rules_hdl//dependency_support:dependency_support.bzl", rules_hdl_dependency_support = "dependency_support")
rules_hdl_dependency_support()


load("@rules_hdl//:init.bzl", rules_hdl_init = "init")
rules_hdl_init(python_interpreter_target = "@rules_hdl_cpython//:install/bin/python3")
