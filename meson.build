project(
  'qucs-netlist',
  version: '0.0.3',
  meson_version: '>= 0.40.0'
)

bindir = get_option('bindir')
datadir = get_option('datadir')
pkgdatadir = join_paths(get_option('prefix'), get_option('datadir'), 'qucs-netlist')

conf = configuration_data()
conf.set('pkgdatadir', pkgdatadir)

configure_file(
  input: 'qucs-netlist.in',
  output: 'qucs-netlist',
  configuration: conf,
  install_dir: bindir
)

data_files = [
  'qucs-netlist.html',  
  'qucs-netlist.dat'
]

foreach file : data_files
  install_data(file, install_dir: pkgdatadir)
endforeach

install_data(
  'qucs-netlist.1',
  install_dir: join_paths(datadir, 'man', 'man1')
)

