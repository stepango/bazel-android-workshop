load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kt_android_library")

kt_android_library(
    name = "notifications",
    srcs = glob(["*.kt"]),
    deps = [
        "//app/src/main:res",
        "@maven//:androidx_lifecycle_lifecycle_extensions"
    ],
    visibility = ["//app/src/main:__subpackages__"],
)