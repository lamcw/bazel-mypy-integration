workspace(name = "bazel_mypy_integration")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load(
    "//repositories:repositories.bzl",
    mypy_integration_repositories = "repositories",
)

mypy_integration_repositories()

load("//repositories:deps.bzl", mypy_integration_deps = "deps")

mypy_integration_deps("//:current_mypy_version.txt")

http_archive(
    name = "buildifier_prebuilt",
    sha256 = "b3fd85ae7e45c2f36bce52cfdbdb6c20261761ea5928d1686edc8873b0d0dad0",
    strip_prefix = "buildifier-prebuilt-5.1.0",
    urls = [
        "https://github.com/keith/buildifier-prebuilt/archive/5.1.0.tar.gz",
    ],
)

load("@buildifier_prebuilt//:deps.bzl", "buildifier_prebuilt_deps")

buildifier_prebuilt_deps()

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

load("@buildifier_prebuilt//:defs.bzl", "buildifier_prebuilt_register_toolchains")

buildifier_prebuilt_register_toolchains()

http_archive(
    name = "com_google_protobuf",
    sha256 = "14e8042b5da37652c92ef6a2759e7d2979d295f60afd7767825e3de68c856c54",
    strip_prefix = "protobuf-3.18.0",
    urls = [
        "https://mirror.bazel.build/github.com/protocolbuffers/protobuf/archive/v3.18.0.tar.gz",
        "https://github.com/protocolbuffers/protobuf/archive/v3.18.0.tar.gz",
    ],
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

http_archive(
    name = "com_github_bazelbuild_buildtools",
    strip_prefix = "buildtools-master",
    url = "https://github.com/bazelbuild/buildtools/archive/master.zip",
)
