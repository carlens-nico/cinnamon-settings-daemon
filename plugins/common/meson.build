common_sources = [
    'csd-keygrab.c',
    'csd-input-helper.c',
    'csd-power-helper.c',
]

common_deps = [
    config_h,
    gtk,
    x11,
    xi,
]

common_inc = include_directories('.')

common_lib = static_library(
    'common_lib',
    common_sources,
    include_directories: [include_dirs, common_inc],
    dependencies: common_deps,
)

common_dep = declare_dependency(
    include_directories: include_dirs,
    link_with: common_lib,
    dependencies: common_deps,
)

helper_sources = [
    'test-input-helper.c',
    common_sources,
]

executable(
    'csd-input-helper',
    helper_sources,
    dependencies: common_dep,
    install: true,
    install_dir: pkglibdir,
)

install_data(
    'input-device-example.sh',
    install_dir: join_paths(datadir, '@0@-@1@'.format(pkgname, api_version)),
)
