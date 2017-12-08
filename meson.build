project('fmt', 'cpp', version: '4.0.1')
subdir('fmt')

fmt_dep = declare_dependency(
 include_directories: ['.'],
 version: '4.0.1',
 link_with: [fmt_lib]
)

pkg = import('pkgconfig')
pkg.generate(
name: 'fmt',
description: 'c++ formatting library',
url: 'https://github.com/fmtlib/fmt',
version: '4.0.1',
libraries: [fmt_lib]
)


