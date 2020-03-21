load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_JVM_EXTERNAL_TAG = "3.0"
RULES_JVM_EXTERNAL_SHA = "62133c125bf4109dfd9d2af64830208356ce4ef8b165a6ef15bbff7460b35c3a"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "androidx.appcompat:appcompat:1.0.2",
        "androidx.core:core-ktx:1.0.2",
        "com.google.android.material:material:1.0.0",
        "androidx.constraintlayout:constraintlayout:1.1.3",
        "androidx.lifecycle:lifecycle-extensions:2.0.0",
        "androidx.navigation:navigation-fragment:2.0.0",
        "androidx.navigation:navigation-ui:2.0.0",
        "androidx.navigation:navigation-fragment-ktx:2.0.0",
        "androidx.navigation:navigation-ui-ktx:2.0.0",
        "androidx.navigation:navigation-runtime-ktx:2.0.0"
    ],
    repositories = [
        "https://maven.google.com",
        "https://jcenter.bintray.com/",
        "https://repo1.maven.org/maven2",
    ],
)

RULES_KOTLIN_VERSION = "legacy-1.3.0"

RULES_KOTLIN_SHA = "4fd769fb0db5d3c6240df8a9500515775101964eebdf85a3f9f0511130885fde"

http_archive(
    name = "io_bazel_rules_kotlin",
    sha256 = RULES_KOTLIN_SHA,
    strip_prefix = "rules_kotlin-%s" % RULES_KOTLIN_VERSION,
    type = "zip",
    urls = ["https://github.com/bazelbuild/rules_kotlin/archive/%s.zip" % RULES_KOTLIN_VERSION],
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")

KOTLIN_VERSION = "1.3.70"

KOTLINC_RELEASE_SHA = "709d782ff707a633278bac4c63bab3026b768e717f8aaf62de1036c994bc89c7"

KOTLINC_RELEASE = {
    "urls": [
        "https://github.com/JetBrains/kotlin/releases/download/v{v}/kotlin-compiler-{v}.zip".format(v = KOTLIN_VERSION),
    ],
    "sha256": KOTLINC_RELEASE_SHA,
}

kotlin_repositories(compiler_release = KOTLINC_RELEASE)

kt_register_toolchains()  # to use the default toolchain, otherwise see toolchains below

android_sdk_repository(
    name = "androidsdk",
)