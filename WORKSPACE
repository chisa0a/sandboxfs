workspace(name = "sandboxfs")

http_archive(
    name = "io_bazel_rules_go",
    url = "https://github.com/bazelbuild/rules_go/releases/download/0.7.0/rules_go-0.7.0.tar.gz",
    sha256 = "91fca9cf860a1476abdc185a5f675b641b60d3acf0596679a27b580af60bf19c",
)

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_register_toolchains",
    "go_repository",
    "go_rules_dependencies",
)

go_register_toolchains(go_version = "host")

go_repository(
    name = "bazel_gopath",
    importpath = "github.com/DarkDNA/bazel-gopath",
    commit = "f83ae8d403d0c826335a5edf4bbd1f7b0cf176e4",

    # bazel-gopath ships with a proto file and also a precompiled version of it.
    # The proto file does not include the right Go options, which confuses
    # Gazelle, so prefer the precompiled version.
    build_file_proto_mode = "disable",
)

go_repository(
    name = "golint",
    importpath = "github.com/golang/lint",
    commit = "6aaf7c34af0f4c36a57e0c429bace4d706d8e931",
)

go_repository(
    name = "org_bazil_fuse",
    importpath = "bazil.org/fuse",
    commit = "371fbbdaa8987b715bdd21d6adc4c9b20155f748",
)

go_repository(
    name = "org_golang_x_sys",
    importpath = "golang.org/x/sys",
    commit = "4b45465282a4624cf39876842a017334f13b8aff",
)

go_rules_dependencies()
