workspace(name = "rules_pyo3")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

################
# Python Rules #
################

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_python",
    sha256 = "9d04041ac92a0985e344235f5d946f71ac543f1b1565f2cdbc9a2aaee8adf55b",
    strip_prefix = "rules_python-0.26.0",
    url = "https://github.com/bazelbuild/rules_python/releases/download/0.26.0/rules_python-0.26.0.tar.gz",
)

load("@rules_python//python:repositories.bzl", "py_repositories")

py_repositories()

##############
# Rust Rules #
##############

http_archive(
    name = "rules_rust",
    sha256 = "9ecd0f2144f0a24e6bc71ebcc50a1ee5128cedeceb32187004532c9710cb2334",
    urls = ["https://github.com/bazelbuild/rules_rust/releases/download/0.29.1/rules_rust-v0.29.1.tar.gz"],
)

load("@rules_rust//rust:repositories.bzl", "rules_rust_dependencies", "rust_register_toolchains")

rules_rust_dependencies()

rust_register_toolchains()

#######################
# PyO3 via Cargo-Raze #
#######################

load("//cargo:crates.bzl", "rules_pyo3_fetch_remote_crates")

rules_pyo3_fetch_remote_crates()

#################
# Example Repos #
#################

local_repository(
    name = "example",
    path = "example",
)
