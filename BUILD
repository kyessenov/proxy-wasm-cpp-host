licenses(["notice"])  # Apache 2

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "include",
    hdrs = [
        "include/proxy-wasm/context.h",
        "include/proxy-wasm/compat.h",
        "include/proxy-wasm/exports.h",
        "include/proxy-wasm/null.h",
        "include/proxy-wasm/word.h",
        "include/proxy-wasm/v8.h",
        "include/proxy-wasm/wasm.h",
        "include/proxy-wasm/wasm_vm.h",
    ],
    copts = ["-std=c++14"],
    deps = [
        "@proxy_wasm_cpp_sdk//:common_lib",
    ],
)

cc_library(
    name = "lib",
    srcs = [
        "src/exports.cc",
        "src/foreign.cc",
        "src/context.cc",
        "src/wasm.cc",
        "src/base64.cc",
        "src/base64.h",
        "src/v8/v8.cc",
        "src/null/null.cc",
        "src/null/null_plugin.cc",
        "src/null/null_plugin.h",
        "src/null/null_vm.cc",
        "src/null/null_vm.h",
        "src/null/null_vm_plugin.h",
        "src/null/wasm_api_impl.h",
    ],
    copts = ["-std=c++14"],
    deps = [
        ":include",
        "@proxy_wasm_cpp_sdk//:api_lib",
        "@proxy_wasm_cpp_sdk//:common_lib",
        "@envoy//external:abseil_strings",
        "@envoy//external:abseil_optional",
        "@envoy//external:zlib",
        "@boringssl//:ssl",
        "@envoy//external:wee8",
        "@envoy//external:protobuf",
    ],
)
