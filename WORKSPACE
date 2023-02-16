load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("@bazel_tools//tools/build_defs/repo:utils.bzl", "maybe")

maybe(
    git_repository,
    name = "rules_hdl",
    remote = "https://github.com/hdl/bazel_rules_hdl",
    commit = "6689294f2d4f45de02a527d947b4703b4c008b53",
    shallow_since = "1676530055 -0800",
)

load("@rules_hdl//dependency_support:dependency_support.bzl", rules_hdl_dependency_support = "dependency_support")
rules_hdl_dependency_support()

load("@rules_hdl//:init.bzl", rules_hdl_init = "init")
rules_hdl_init()
