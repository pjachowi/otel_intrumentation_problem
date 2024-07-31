load("@rules_python//python:pip.bzl", "compile_pip_requirements")
load("@py_deps//:requirements.bzl", "requirement")

compile_pip_requirements(
    name = "requirements",
    extra_args = ["--allow-unsafe"],
    requirements_in = "requirements.in",
    requirements_txt = "requirements_lock.txt",
    timeout = "moderate",
)

py_binary(
    name = "test",
    srcs = ["test.py"],
    main = "test.py",
    deps = [
        requirement("opentelemetry-exporter-otlp"),
        requirement("opentelemetry-instrumentation-grpc"),
    ],
)
