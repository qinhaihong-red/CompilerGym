# This package contains a modified implementation of inst2vec.

genrule(
    name = "dictionary",
    srcs = ["dictionary.tar.bz2"],
    outs = ["dictionary.pickle"],
    cmd = "tar xjf $< -C $(@D)",
)

genrule(
    name = "embeddings",
    srcs = ["embeddings.tar.bz2"],
    outs = ["embeddings.pickle"],
    cmd = "tar xjf $< -C $(@D)",
)

py_library(
    name = "inst2vec",
    srcs = ["__init__.py"],
    data = [
        ":dictionary",
        ":embeddings",
    ],
    visibility = ["//visibility:public"],
    deps = [
        ":inst2vec_preprocess",
        "//compiler_gym/util",
    ],
)

py_library(
    name = "inst2vec_preprocess",
    srcs = ["inst2vec_preprocess.py"],
    deps = [
        ":inst2vec_utils",
        ":rgx_utils",
    ],
)

py_library(
    name = "inst2vec_utils",
    srcs = ["inst2vec_utils.py"],
)

py_library(
    name = "rgx_utils",
    srcs = ["rgx_utils.py"],
)
