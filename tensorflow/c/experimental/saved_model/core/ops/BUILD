# This package contains written convenience helpers for Eager Operations
# used by SavedModel. Once we autogenerate C++ Eager Op wrappers, we can remove these.
load(
    "//tensorflow:tensorflow.bzl",
    "tf_cc_test",
)

package(
    default_visibility = [
        # Restricting visibility for now
        "//tensorflow/c/experimental/saved_model/core:__subpackages__",
        "//tensorflow/c/experimental/saved_model/internal:__subpackages__",
    ],
    licenses = ["notice"],  # Apache 2.0
)

cc_library(
    name = "variable_ops",
    srcs = [
        "variable_ops.cc",
    ],
    hdrs = [
        "variable_ops.h",
    ],
    deps = [
        "//tensorflow/c/eager:abstract_operation",
        "//tensorflow/c/eager:abstract_tensor_handle",
        "//tensorflow/c/eager:immediate_execution_context",
        "//tensorflow/c/eager:immediate_execution_operation",
        "//tensorflow/c/eager:immediate_execution_tensor_handle",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core:protos_all_cc",
        "//tensorflow/core/lib/llvm_rtti",
        "@com_google_absl//absl/types:span",
    ],
)

tf_cc_test(
    name = "variable_ops_test",
    srcs = [
        "variable_ops_test.cc",
    ],
    deps = [
        ":variable_ops",
        "//tensorflow/c:tensor_interface",
        "//tensorflow/c/eager:abstract_tensor_handle",
        "//tensorflow/c/eager:immediate_execution_context",
        "//tensorflow/c/eager:immediate_execution_tensor_handle",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core:protos_all_cc",
        "//tensorflow/core:test",
        "//tensorflow/core:test_main",
        "//tensorflow/core/common_runtime:core_cpu_lib",
        "//tensorflow/core/common_runtime/eager:context",
        "//tensorflow/core/common_runtime/eager:core",
    ],
)
