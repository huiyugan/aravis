po_dir = join_paths (meson.source_root (), 'po')

appdata_conf = configuration_data()
appdata_conf.set ('ARAVIS_API_VERSION', aravis_api_version)

configure_file (input: files('arv-viewer.appdata.xml.in'),
		output: 'arv-viewer.appdata.xml',
		configuration: appdata_conf,
		install_dir: desktopdir)

desktop_conf = configuration_data()

desktop = i18n.merge_file ('desktop',
			   input: configure_file (input: files('arv-viewer.desktop.in.in'),
						  output: 'arv-viewer.desktop.in',
						  configuration: desktop_conf),
			   output: 'arv-viewer.desktop',
			   install: true,
			   install_dir: desktopdir,
			   po_dir: po_dir,
			   type: 'desktop')

