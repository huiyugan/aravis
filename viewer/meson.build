sources = [
	'main.c',
	'arvviewer.c'
]

headers = [
	'arvviewertypes.h',
	'arvviewer.h'
]

cflags = [
	'-I../src',
	'-DPACKAGE_LOCALE_DIR="@0@/locale"'.format (get_option ('prefix')),
	'-DARAVIS_DATA_DIR="@0@"'.format (get_option ('datadir')),
	'-DARAVIS_API_VERSION="@0@"'.format (aravis_api_version),
	'-DARAVIS_ICON_DIR="@0@/icons"'.format (get_option ('datadir'))
]

executable ( 'arv-viewer', sources,
	link_with: aravis_library,
	c_args: cflags,
	include_directories: [configuration_inc, library_inc],
	dependencies: aravis_viewer_dependencies)
