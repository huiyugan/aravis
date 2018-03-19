tests = [
	['evaluator',	['-I../src']],
	['buffer', 	['-I../src']],
	['misc', 	['-I../src']],
	['fake',	['-I../src', '-DGENICAM_FILENAME="../src/arv-fake-camera.xml"']],
	['fakegv',	['-I../src', '-DGENICAM_FILENAME="../src/arv-fake-camera.xml"']],
	['genicam',	['-I../src', '-DGENICAM_FILENAME="../tests/data/genicam.xml"']]
]

foreach t: tests
  exe = executable (t[0], '@0@.c'.format (t[0]),
    c_args: [t[1]],
    link_with: aravis_library,
    dependencies: aravis_dependencies,
    include_directories: [configuration_inc, library_inc])
  test (t[0], exe)
endforeach

examples = [
	['arv-device-test',		'arvdevicetest.c'],
	['arv-genicam-test',		'arvgenicamtest.c'],
	['arv-evaluator-test',	  	'arvevaluatortest.c'],
	['arv-zip-test',		'arvziptest.c'],
	['arv-camera-test',		'arvcameratest.c'],
	['arv-chunk-parser-test',	'arvchunkparsertest.c'],
	['arv-heartbeat-test',		'arvheartbeattest.c'],
	['arv-acquisition-test',	'arvacquisitiontest.c'],
	['arv-example',			'arvexample.c'],
	['arv-auto-packet-size-test',	'arvautopacketsizetest.c'],
	['time-test',			'timetest.c'],
	['realtime-test',		'realtimetest.c'],
	['load-http-test',		'loadhttptest.c'],
]

foreach example: examples
  exe = executable (example[0], example[1],
    c_args: '-I../src',
    link_with: aravis_library,
    dependencies: aravis_dependencies,
    include_directories: [configuration_inc, library_inc])
endforeach
