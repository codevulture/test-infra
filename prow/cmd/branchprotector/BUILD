load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["protect.go"],
    importpath = "k8s.io/test-infra/prow/cmd/branchprotector",
    visibility = ["//visibility:public"],
    deps = [
        "//prow/config:go_default_library",
        "//prow/github:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "protect_test.go",
    ],
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/prow/cmd/branchprotector",
    deps = [
        "//prow/config:go_default_library",
        "//prow/github:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)

go_binary(
    name = "branchprotector",
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/prow/cmd/branchprotector",
    visibility = ["//visibility:public"],
)