project ('aravis', 'c', 'cpp', version: '0.5.11')

gnome = import('gnome')

aravis_version = meson.project_version ()
aravis_api_version = '0.6'

versions = aravis_version.split ('.')
aravis_major_version = versions[0].to_int ()
aravis_minor_version = versions[1].to_int ()
aravis_micro_version = versions[2].to_int ()

cc = meson.get_compiler ('c')
cxx = meson.get_compiler ('cpp')

glib_dep = dependency ('glib-2.0', required: true)
gobject_dep = dependency ('gobject-2.0', required: true)
gio_dep = dependency ('gio-2.0', required: true)
xml2_dep = dependency ('libxml-2.0', required: true)
libz_dep = dependency ('zlib', required: true)

libm = cc.find_library ('m', required: true)

aravis_dependencies = [glib_dep, gobject_dep, gio_dep, xml2_dep, libz_dep, libm]

enable_packet_socket = get_option ('packet-socket')
if enable_packet_socket
	aravis_dependencies += dependency ('libcap-ng', required: true)
	aravis_dependencies += dependency ('audit', required: true)
endif

enable_usb = get_option ('usb')
if enable_usb
	aravis_dependencies += dependency ('libusb-1.0', required: true)
endif

config_data = configuration_data ()
config_data.set_quoted ('PACKAGE_VERSION', aravis_version)
config_data.set ('ARAVIS_BUILD_PACKET_SOCKET', enable_packet_socket)
config_data.set ('ARAVIS_BUILD_USB', enable_usb)
config_data.set ('ARAVIS_FAST_HEARTBEAT', get_option ('fast-heartbeat'))
configure_file (input: 'arvconfig.h.in', output: 'arvconfig.h', configuration: config_data)
configuration_inc = include_directories ('.')

subdir ('src')
subdir ('tests')
subdir ('viewer')

if get_option ('documentation')
	subdir ('docs')
endif
