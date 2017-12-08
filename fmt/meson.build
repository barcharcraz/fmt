compiler = meson.get_compiler('cpp')
have_open = compiler.has_function('open', prefix: '#include <io.h>') or compiler.has_function('open', prefix: '#include <fcntl.h>')
fmt_headers = files(
'container.h',
'format.h',
'ostream.h',
'printf.h',
'string.h',
'time.h'
)

fmt_sources = files(
'format.cc',
'ostream.cc',
'printf.cc'
)

if have_open
    fmt_headers += files('posix.h')
    fmt_sources += files('posix.cc')
endif

opts = []
if get_option('default_library') == 'shared'
   opts += ['-DPRIVATE', '-DFMT_EXPORT', '-DINTERFACE', '-DFMT_SHARED']
endif

fmt_lib = library('fmt', fmt_sources, cpp_args: opts, implicit_include_directories: false)

install_headers(fmt_headers, subdir:'fmt')
