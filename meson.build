project('sbpd', ['c'],
    version: '1.0',
    license: 'MIT',
    default_options: [
        'c_std=gnu99',
        'prefix=/usr',
        'sysconfdir=/etc',
        'localstatedir=/var',
        'buildtype=debug'
    ],
    meson_version: '>= 0.41',

)

cc = meson.get_compiler('c')

dep = dependency('libcurl')
libwiringpi_dep = cc.find_library('wiringPi')

sources = files('''
    sbpd.c
    sbpd.h
    GPIO.c
    GPIO.h
    control.c
    control.h
    discovery.c
    discovery.h
    servercomm.c
    servercomm.h
'''.split())

sbpd = executable(
    'sbpd',
    [sources],
    dependencies: [
      dep,
      libwiringpi_dep
    ],
    install: true
)

