licenses(["restricted"])

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "python_headers",
    hdrs = glob([
        "python_include/**/*.h",
    ]),
    data = [":python_checked"],
    includes = ["python_include"],
)

genrule(
    name = "python_check",
    srcs = [
        "python_config.sh",
    ],
    outs = [
        "python_checked",
    ],
    cmd = "OUTPUTDIR=\"$(@D)/\"; ./util/python/python_config.sh --check && touch $$OUTPUTDIR/python_checked",
    local = 1,
)
