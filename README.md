Steps to reproduce the problem:
1. `bazelisk run //:requirements.update`
2. `bazelisk run //:test`

Output on my machine:
```
$ bazelisk run //:test
INFO: Analyzed target //:test (73 packages loaded, 4272 targets configured).
INFO: Found 1 target...
Target //:test up-to-date:
  bazel-bin/test
INFO: Elapsed time: 0.401s, Critical Path: 0.04s
INFO: 1 process: 1 internal.
INFO: Build completed successfully, 1 total action
INFO: Running command line: bazel-bin/test
Traceback (most recent call last):
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/execroot/__main__/bazel-out/k8-fastbuild/bin/test.runfiles/__main__/test.py", line 1, in <module>
    from opentelemetry.instrumentation import grpc
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/execroot/__main__/bazel-out/k8-fastbuild/bin/test.runfiles/py_deps_opentelemetry_instrumentation_grpc/site-packages/opentelemetry/instrumentation/grpc/__init__.py", line 291, in <module>
    from opentelemetry.instrumentation.instrumentor import BaseInstrumentor
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/execroot/__main__/bazel-out/k8-fastbuild/bin/test.runfiles/py_deps_opentelemetry_instrumentation/site-packages/opentelemetry/instrumentation/instrumentor.py", line 27, in <module>
    from opentelemetry.instrumentation.dependencies import (
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/execroot/__main__/bazel-out/k8-fastbuild/bin/test.runfiles/py_deps_opentelemetry_instrumentation/site-packages/opentelemetry/instrumentation/dependencies.py", line 4, in <module>
    from pkg_resources import (
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/execroot/__main__/bazel-out/k8-fastbuild/bin/test.runfiles/py_deps_setuptools/site-packages/pkg_resources/__init__.py", line 96, in <module>
    from jaraco.text import (
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/execroot/__main__/bazel-out/k8-fastbuild/bin/test.runfiles/py_deps_setuptools/site-packages/setuptools/_vendor/jaraco/text/__init__.py", line 231, in <module>
    files(__name__).joinpath('Lorem ipsum.txt').read_text(encoding='utf-8')
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/external/python3_9_x86_64-unknown-linux-gnu/lib/python3.9/pathlib.py", line 1266, in read_text
    with self.open(mode='r', encoding=encoding, errors=errors) as f:
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/external/python3_9_x86_64-unknown-linux-gnu/lib/python3.9/pathlib.py", line 1252, in open
    return io.open(self, mode, buffering, encoding, errors, newline,
  File "/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/external/python3_9_x86_64-unknown-linux-gnu/lib/python3.9/pathlib.py", line 1120, in _opener
    return self._accessor.open(self, flags, mode)
FileNotFoundError: [Errno 2] No such file or directory: '/home/nobody/.cache/bazel/_bazel_nobody/b0c935cccbea1e51f1a6303d0c0ad81d/execroot/__main__/bazel-out/k8-fastbuild/bin/test.runfiles/py_deps_setuptools/site-packages/setuptools/_vendor/jaraco/text/Lorem ipsum.txt'

```
