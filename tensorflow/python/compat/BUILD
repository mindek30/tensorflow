load("//tensorflow:tensorflow.bzl", "tf_py_test")

package(
    licenses = ["notice"],  # Apache 2.0
)

py_library(
    name = "v2_compat",
    srcs = ["v2_compat.py"],
    srcs_version = "PY2AND3",
    visibility = ["//tensorflow:internal"],
    deps = [
        "//tensorflow/python:control_flow_v2_toggles",
        "//tensorflow/python:tf2",
        "//tensorflow/python:util",
        "//tensorflow/python/eager:monitoring",
    ],
)

py_library(
    name = "compat",
    srcs = ["compat.py"],
    srcs_version = "PY2AND3",
    visibility = ["//tensorflow:internal"],
    deps = [
        "//tensorflow/python:util",
    ],
)

tf_py_test(
    name = "compat_test",
    size = "small",
    srcs = ["compat_test.py"],
    tags = ["nofwdcompat"],
    tfrt_enabled = True,
    deps = [
        ":compat",
        "//tensorflow/python:client_testlib",
    ],
)

tf_py_test(
    name = "disable_v2_behavior_test",
    size = "small",
    srcs = ["disable_v2_behavior_test.py"],
    tfrt_enabled = True,
    deps = [
        ":v2_compat",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
    ],
)
