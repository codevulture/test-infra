load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["approve.go"],
    importpath = "k8s.io/test-infra/prow/plugins/approve",
    visibility = ["//visibility:public"],
    deps = [
        "//prow/github:go_default_library",
        "//prow/pluginhelp:go_default_library",
        "//prow/plugins:go_default_library",
        "//prow/plugins/approve/approvers:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["approve_test.go"],
    data = [
        "//prow:configs",
    ],
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/prow/plugins/approve",
    deps = [
        "//prow/github:go_default_library",
        "//prow/github/fakegithub:go_default_library",
        "//prow/plugins:go_default_library",
        "//vendor/github.com/ghodss/yaml:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/sets:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//prow/plugins/approve/approvers:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
