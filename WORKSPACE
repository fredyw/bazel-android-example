
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_android",
    sha256 = "d0b310dd23442b8ff024cba73ad7564024b473673d8d5de7d01bd91adb9aa2d0",
    strip_prefix = "rules_android-dd7b90c91fdc4edeca90ba9ebffa3c469b426a35",
    url = "https://github.com/bazelbuild/rules_android/archive/dd7b90c91fdc4edeca90ba9ebffa3c469b426a35.zip",
)

load("@rules_android//:prereqs.bzl", "rules_android_prereqs")

rules_android_prereqs()

load("@rules_android//:defs.bzl", "rules_android_workspace")

rules_android_workspace()

load("@rules_android//rules:rules.bzl", "android_sdk_repository")

android_sdk_repository(
    name = "androidsdk",
)

register_toolchains(
    "@rules_android//toolchains/android:android_default_toolchain",
    "@rules_android//toolchains/android_sdk:android_sdk_tools",
)

http_archive(
    name = "rules_android_ndk",
    sha256 = "65aedff0cd728bee394f6fb8e65ba39c4c5efb11b29b766356922d4a74c623f5",
    strip_prefix = "rules_android_ndk-0.1.2",
    url = "https://github.com/bazelbuild/rules_android_ndk/releases/download/v0.1.2/rules_android_ndk-v0.1.2.tar.gz",
)

load("@rules_android_ndk//:rules.bzl", "android_ndk_repository")

android_ndk_repository(name = "androidndk")

register_toolchains("@androidndk//:all")
