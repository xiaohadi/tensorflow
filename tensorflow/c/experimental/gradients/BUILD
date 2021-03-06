load("//tensorflow:tensorflow.bzl", "filegroup")
load("//tensorflow/core/platform:rules_cc.bzl", "cc_library")

# Library of gradient functions.
package(
    licenses = ["notice"],  # Apache 2.0
)

cc_library(
    name = "array_grad",
    srcs = ["array_grad.cc"],
    hdrs = [
        "array_grad.h",
    ],
    visibility = [
        "//tensorflow:internal",
    ],
    deps = [
        "//tensorflow/c/eager:abstract_operation",
        "//tensorflow/c/eager:abstract_tensor_handle",
        "//tensorflow/c/eager:c_api_unified_internal",
        "//tensorflow/c/eager:gradients_internal",
        "//tensorflow/core/lib/llvm_rtti",
    ],
)

cc_library(
    name = "math_grad",
    srcs = ["math_grad.cc"],
    hdrs = [
        "math_grad.h",
    ],
    visibility = [
        "//tensorflow:internal",
    ],
    deps = [
        "//tensorflow/c/eager:abstract_tensor_handle",
        "//tensorflow/c/eager:gradients_internal",
        "//tensorflow/c/experimental/ops:array_ops",
        "//tensorflow/c/experimental/ops:math_ops",
        "//tensorflow/c/experimental/ops:nn_ops",
    ],
)

cc_library(
    name = "nn_grad",
    srcs = ["nn_grad.cc"],
    hdrs = [
        "nn_grad.h",
    ],
    visibility = [
        "//tensorflow:internal",
    ],
    deps = [
        "//tensorflow/c/eager:abstract_tensor_handle",
        "//tensorflow/c/eager:gradients_internal",
        "//tensorflow/c/eager:immediate_execution_context",
        "//tensorflow/c/eager:immediate_execution_tensor_handle",
        "//tensorflow/c/experimental/ops:array_ops",
        "//tensorflow/c/experimental/ops:math_ops",
        "//tensorflow/c/experimental/ops:nn_ops",
        "//tensorflow/core/lib/llvm_rtti",
        "//tensorflow/core/platform:errors",
        "@com_google_absl//absl/types:span",
    ],
)

cc_library(
    name = "gradients",
    hdrs = [
        "array_grad.h",
        "math_grad.h",
        "nn_grad.h",
    ],
    visibility = [
        "//tensorflow:internal",
    ],
    deps = [
        ":array_grad",
        ":math_grad",
        ":nn_grad",
        "//tensorflow/c/eager:gradients_internal",
    ],
)

filegroup(
    name = "pywrap_required_hdrs",
    srcs = [
        "array_grad.h",
        "math_grad.h",
        "nn_grad.h",
    ],
    visibility = [
        "//tensorflow/core:__pkg__",
        "//tensorflow/python:__pkg__",
    ],
)
