# Description:
#   TensorFlow C++ inference example for labeling images.

package(
    default_visibility = ["//tensorflow:internal"],
    features = [
        "-layering_check",
        "-parse_headers",
    ],
)

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

cc_library(
    name = "wav_to_spectrogram_lib",
    srcs = ["wav_to_spectrogram.cc"],
    hdrs = ["wav_to_spectrogram.h"],
    deps = [
        "//tensorflow/cc:cc_ops",
        "//tensorflow/core:core_cpu",
        "//tensorflow/core:framework",
        "//tensorflow/core:framework_internal",
        "//tensorflow/core:lib",
        "//tensorflow/core:tensorflow",
    ],
)

cc_binary(
    name = "wav_to_spectrogram",
    srcs = ["main.cc"],
    deps = [
        ":wav_to_spectrogram_lib",
        "//tensorflow/core:framework_internal",
        "//tensorflow/core:lib",
    ],
)

cc_test(
    name = "wav_to_spectrogram_test",
    size = "medium",
    srcs = ["wav_to_spectrogram_test.cc"],
    deps = [
        ":wav_to_spectrogram_lib",
        "//tensorflow/core:lib",
        "//tensorflow/core:lib_internal",
        "//tensorflow/core:test",
        "//tensorflow/core:test_main",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
            "bin/**",
            "gen/**",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
