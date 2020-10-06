package(default_visibility = ['//visibility:public'])
load("@mxebzl//tools:rules.bzl", "pkg_winzip")

cc_binary(
    name = 'hello',
    srcs = ['hello.c'],
)

pkg_winzip(
    name = "hello-windows",
    files = [
        ":hello",
        # maybe some other non-exe resources, like a 'content' directory.
    ],
    skip_dlls = [
        # Any system DLLs the dependency analyzer says you need but you
        # aren't shipping with your package.
        # "winmm.dll",
        # etc...
    ],
    zips = [
        # Any additional content you want to combine into your package
        # (e.g. "@mxebzl//runtime/python37")
    ],
    #out = "whatever.zip", # Optional: defaults to ${name}.zip
)
