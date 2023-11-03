# Bazel rules for [jq](https://github.com/stedolan/jq)

## Installation

Include this in your WORKSPACE file:

```starlark
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_jq",
    url = "https://github.com/jqlang/bazel_rules_jq/releases/download/0.0.0/rules_jq-v0.0.0.tar.gz",
    sha256 = "",
)

load("@rules_jq//jq:repositories.bzl", "jq_register_toolchains", "rules_jq_dependencies")

rules_jq_dependencies()

jq_register_toolchains(
    name = "jq",
    jq_version = "1.7",
)
```

> note, in the above, replace the version and sha256 with the one indicated
> in the release notes for rules_jq.
