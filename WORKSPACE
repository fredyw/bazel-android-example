
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_kotlin",
    sha256 = "34e8c0351764b71d78f76c8746e98063979ce08dcf1a91666f3f3bc2949a533d",
    url = "https://github.com/bazelbuild/rules_kotlin/releases/download/v1.9.5/rules_kotlin-v1.9.5.tar.gz",
)

load("@rules_kotlin//kotlin:repositories.bzl", "kotlin_repositories")

kotlin_repositories()

load("@rules_kotlin//kotlin:core.bzl", "kt_register_toolchains")

kt_register_toolchains()

http_archive(
    name = "rules_android",
    sha256 = "b1599e4604c1594a1b0754184c5e50f895a68f444d1a5a82b688b2370d990ba0",
    strip_prefix = "rules_android-0.5.1",
    url = "https://github.com/bazelbuild/rules_android/releases/download/v0.5.1/rules_android-v0.5.1.tar.gz",
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
