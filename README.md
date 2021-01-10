# qucs-netlist
Will export a netlist from a Qucs schematic which is suitable for a PCB design application. 
It will run with Qucs installed from a Debian package (qucs) or from a Snap (qucs-spice.qucs), but not from qucs-s.

INSTALLATION

qucs-netlist_all .deb can't be installed with the "Software" application as it is not a complete Debian package, but if it is downloaded into your home directory it can be installed with:

      sudo dpkg -i qucs-netlist_all.deb

Check the program's properties and make sure there is a tick in Permissions - Allow executing file as program.


TO RUN

In a terminal, cd to the directory with your QUCS schematic in, then type 

		qucs-netlist mycircuit.sch

The output file will be called mycircuit.net 

If you run it again it will not overwrite the existing file, unless you add -y at the end of the line:

		qucs-netlist mycircuit.sch -y

FILES

qucs-netlist is the program.
qucs-netlist.html is the help file.
qucs-netlist.dat links Qucs component names with VeroRoute ones.
qucsparts.sch is a Qucs schematic containing all the parts that the program can process. It can be used for a test of the program.

ERRORS

The program calls a qucs process which produces many lines (100+) of errors in the terminal. They are mostly to do with missing fonts and don't affect the output file. 
The program will print a warning line for a component not yet in the data file:
  Warning: Unknown component type not converted: D2 Diac

SCOPE

The exported file can be imported by DIY Layout Creator (from their website and soon from Flathub) and VeroRoute, but it could be used by another application provided it accepted the component types in the qucsnet.dat file. Alternatively another .dat file could be provided with component names acceptable to the application.

