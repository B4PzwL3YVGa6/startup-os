package(default_visibility = ["//visibility:public"])

load("//tools/checkstyle:checkstyle.bzl", "checkstyle_test")

java_binary(
    name = "test_tool",
    srcs = [
        "TestTool.java",
    ],
    main_class = "com.google.startupos.common.repo.tests.TestTool",
    deps = [
        "//common",
        "//common:dagger_with_annotation_processor",
        "//common/repo",
        "//common/repo:repo_java_proto",
        "//third_party/maven/com/google/flogger:flogger_system_backend",
        "//third_party/maven/javax/inject:javax_inject",
        "//third_party/maven/org/slf4j:slf4j_simple",
        "//tools/reviewer/local_server/service:code_review_java_proto",
    ],
)

checkstyle_test(
    name = "test_tool-checkstyle",
    allow_failure = 1,
    target = ":test_tool",
)

java_test(
    name = "GitRepoTest",
    srcs = [
        "GitRepoTest.java",
    ],
    test_class = "com.google.startupos.common.repo.tests.GitRepoTest",
    deps = [
        "//common",
        "//common:dagger_with_annotation_processor",
        "//common/flags",
        "//common/repo",
        "//common/repo:repo_java_proto",
        "//third_party/maven/com/google/guava",
        "//third_party/maven/com/google/jimfs",
        "//third_party/maven/junit",
        "//third_party/maven/org/mockito:mockito_core",
        "//third_party/maven/org/objenesis",
    ],
)

checkstyle_test(
    name = "GitRepoTest-checkstyle",
    allow_failure = 1,
    target = ":GitRepoTest",
)
