package(default_visibility = ["//visibility:public"])

load("//tools/checkstyle:checkstyle.bzl", "checkstyle_test")

proto_library(
    name = "build_file_generator_proto",
    srcs = ["build_file_generator.proto"],
)

java_proto_library(
    name = "build_file_generator_java_proto",
    deps = [":build_file_generator_proto"],
)

java_library(
    name = "build_file_generator",
    srcs = [
        "JavaClassAnalyzer.java",
        "ProtoFileAnalyzer.java",
    ],
    deps = [
        "build_file_generator_java_proto",
        "//common",
        "//common:dagger_with_annotation_processor",
        "//third_party/maven/com/google/guava",
        "//third_party/maven/javax/inject:javax_inject",
    ],
)

checkstyle_test(
    name = "build_file_generator-checkstyle",
    allow_failure = 1,
    target = ":build_file_generator",
)

java_binary(
    name = "build_file_generator_tool",
    srcs = ["BuildFileGeneratorTool.java"],
    main_class = "com.google.startupos.tools.buildfilegenerator.BuildFileGeneratorTool",
    deps = [
        ":build_file_generator",
        ":build_file_generator_java_proto",
        "//common",
        "//common:dagger_with_annotation_processor",
        "//common/flags",
        "//third_party/maven/com/google/flogger:flogger_system_backend",
        "//third_party/maven/javax/inject:javax_inject",
    ],
)

checkstyle_test(
    name = "build_file_generator_tool-checkstyle",
    allow_failure = 1,
    target = ":build_file_generator_tool",
)
