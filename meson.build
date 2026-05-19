project(
  'libpng',
  'c',
  version: '1.6.58',
  license: 'libpng-2.0',
  meson_version: '>= 1.0.0',
  default_options: [
    'c_std=c99',
    'warning_level=1',
    'default_library=static',
  ],
)

zlib_dep = dependency('zlib')

libpng_sources = files(
  'src/png.c',
  'src/pngerror.c',
  'src/pngget.c',
  'src/pngmem.c',
  'src/pngpread.c',
  'src/pngread.c',
  'src/pngrio.c',
  'src/pngrtran.c',
  'src/pngrutil.c',
  'src/pngset.c',
  'src/pngtrans.c',
  'src/pngwio.c',
  'src/pngwrite.c',
  'src/pngwtran.c',
  'src/pngwutil.c',
)

libpng_internal_inc = include_directories('src', 'include/png')
libpng_public_inc = include_directories('include', is_system: true)

libpng_lib = static_library(
  'png',
  libpng_sources,
  include_directories: libpng_internal_inc,
  dependencies: zlib_dep,
)

libpng_dep = declare_dependency(
  link_with: libpng_lib,
  include_directories: libpng_public_inc,
  dependencies: zlib_dep,
)

meson.override_dependency('libpng', libpng_dep)
