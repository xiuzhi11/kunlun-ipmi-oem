project(
    'kunlun-ipmi-oem',
    'cpp',
    default_options: [
        'warning_level=3',
        'werror=true',
        'cpp_std=c++17',
        'prefix=/usr',
        'b_lundef=false',
        'buildtype=debugoptimized',
    ],
    license: 'Apache-2.0',
    version: '1.0',
    meson_version: '>=0.49.0',
)

phosphor_logging = dependency('phosphor-logging')
libipmid = dependency('libipmid')

# Common configurations for src and test
cdata = configuration_data()
cdata.set_quoted('IPMI_BIOSDATA_DIR', get_option('IPMI_BIOSDATA_DIR'))

subdir('src')

build_tests = get_option('tests')
if not build_tests.disabled()
    subdir('test')
endif
