package(default_visibility = ["//visibility:public"])

load("@envoy//bazel:envoy_build_system.bzl", "envoy_cc_binary", "envoy_cc_library")

envoy_cc_binary(
    name = "envoy",
    repository = "@envoy",
    deps = [
        ":echo2_config",
        "@envoy//source/exe:envoy_main_lib"
    ],
)

envoy_cc_library(
    name = "echo2_lib",
    srcs = ["echo2.cc"],
    hdrs = ["echo2.h"],
    deps = [
        "@envoy//include/envoy/buffer:buffer_interface",
        "@envoy//include/envoy/network:connection_interface",
        "@envoy//include/envoy/network:filter_interface",
        "@envoy//source/common/common:assert_lib",
        "@envoy//source/common/common:logger_lib",
    ],
    repository = "@envoy",
)

envoy_cc_library(
    name = "echo2_config",
    srcs = ["echo2_config.cc"],
    deps = [
        ":echo2_lib",
        "@envoy//include/envoy/network:connection_interface",
        "@envoy//source/server:configuration_lib",
    ],
    alwayslink = 1,
    repository = "@envoy",
)
