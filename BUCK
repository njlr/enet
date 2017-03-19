macos_sources = [
  'unix.c',
]

linux_sources = [
  'unix.c',
]

windows_sources = [
  'win32.c',
]

platform_sources = macos_sources + linux_sources + windows_sources

cxx_library(
  name = 'enet',
  header_namespace = 'enet',
  exported_headers = subdir_glob([
    ('include/enet', '**/*.h'),
  ]),
  srcs = glob([
    '*.c',
  ],
  excludes = platform_sources),
  platform_srcs = [
    ('default', macos_sources),
    ('^macos.*', macos_sources),
    ('^linux.*', linux_sources),
    ('^windows.*', windows_sources),
  ],
  visibility = [
    'PUBLIC',
  ],
)
