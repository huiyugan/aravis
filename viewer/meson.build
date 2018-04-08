viewer_sources = [
	'main.c',
	'arvviewer.c'
]

viewer_headers = [
	'arvviewertypes.h',
	'arvviewer.h'
]

viewer_c_args = [
	'-I../src',
	'-DPACKAGE_LOCALE_DIR="@0@/locale"'.format (get_option ('prefix')),
	'-DARAVIS_DATA_DIR="@0@"'.format (get_option ('datadir')),
	'-DARAVIS_API_VERSION="@0@"'.format (aravis_api_version),
	'-DARAVIS_ICON_DIR="@0@/icons"'.format (get_option ('datadir'))
]

executable ( 'arv-viewer', viewer_sources, viewer_headers,
	link_with: aravis_library,
	c_args: viewer_c_args,
	include_directories: [configuration_inc, library_inc],
	dependencies: aravis_viewer_dependencies,
	install: true)

subdir ('data')
