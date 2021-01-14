# qucs-netlist
Will export a netlist from a Qucs schematic which is suitable for a PCB design application. 
It uses a Qucs schematic file to add components to a netlist file.
If there is also a Qucs .sim file with the same name but the .sim extension, it will use that to create the nets, if not it will attempt to run Qucs to create a .sim file, if Qucs has been installed from a Debian package (qucs) or from a Snap (qucs-spice.qucs), that should succeed, but it won't work from from qucs-s.
If no .sim file was present and can't be created, the output netlist file will contain components but no nets.

==LINUX==

INSTALLATION

Download qucs-netlist_0.0.3_all.deb and double-clicking on it to install it.

RUNNING
The program cannot be run from your application menu as it needs a filename. In a terminal, cd to the directory with your QUCS schematic in, then type 

		qucs-netlist mycircuit.sch

The output file will be called mycircuit.net 

If you run it again it will not overwrite the existing file, unless you add -y at the end of the line:

		qucs-netlist mycircuit.sch -y

==OTHER SYSTEMS==

INSTALLATION

Your system must have Python3 installed (and QUCS if that is available for your system). If Qucs is not available you could edit out the part of the program that uses it, but the output file will only contain a parts list there will be no nets.

Download the files and copy them into a convenient directory:
	qucs-netlist.py is the program.
	qucs-netlist.html is the help file.
	qucs-netlist.dat links Qucs component names with VeroRoute ones.
	qucsparts.sch is a Qucs schematic containing all the parts that the program can process. It can be used for a test of the program.
Use your file manager to edit the properties of the program file and make it executable.


RUNNING
Copy the QUCS schematic to your qucs-netlist directory, then in a terminal, cd to that directory, then type 

		{route to directory}qucs-netlist.py mycircuit.sch

The output file will be called mycircuit.net 

If you run it again it will not overwrite the existing file, unless you add -y at the end of the line:

		qucs-netlist mycircuit.sch -y

ERRORS TO IGNORE

The program calls a qucs process which produces many lines (100+) of errors in the terminal. They are mostly to do with missing fonts and don't affect the output file. 
The program will print a warning line for a component not yet in the data file:
  Warning: Unknown component type not converted: D2 Diac

SCOPE

The exported file can be imported by DIY Layout Creator (from their website and soon from Flathub) and VeroRoute, but it could be used by another application provided it accepted the component types in the qucsnet.dat file. Alternatively another .dat file could be provided with component names acceptable to the application.

