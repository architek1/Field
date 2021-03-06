## Field

Field is an open-source software project initiated by OpenEndedGroup, for the creation of their digital artworks. It is an environment for writing code to rapidly and experimentally assemble and explore algorithmic systems. It is _visual_, it is _hybrid_, it is _code-based_. We think that it has something to offer a diverse range of programmers and artists. It is developed and tested on Mac OS X (primarily) and Ubuntu 12 + Nvidia proprietary drivers.

*Our main documentation website is here: http://openendedgroup.com/field*

### Building

To build Field:

	git clone git://github.com/OpenEndedGroup/Field.git
	cd Field/Contents
	ant


That will build the core of Field. Individual plugins have additional targets inside the `build.xml` file. If want to build them all (and have both Max/MSP and Processing 2.0b1 installed) then `ant extras_all`. For the less bold, you can add individual plugins: `extras_jsrscripting` adds nascant support for other languages (including Clojure and Ruby); `extras_online` adds a plugin that lets you write in-browser JavaScript; `extras_jfbxlib` brings in fbx support and so on. See the `build.xml` file for a list of targets.

### The workspace

On first launch Field will ask where you want to store your Field files (it will suggest ~/Documents/FieldWorkspace). It will also check to see if you have Mercurial installed. To start with the [the tutorials](http://openendedgroup.com/field/FieldGATech), simply uncompress them and put them inside your workspace.

### Running --- Mac OS X

This repository is _inside_ a Mac OS X Application structure. That is, if you name this repository `field.app` then you'll have a double-clickable Mac app. 

If you are on OS X you probably want to set this:

	defaults write com.openendedgroup.Field use16 YES

This tells Field to launch using an OS installed 1.6 VM. If you want to use an OpenJDK 1.7 VM place the .jdk bundle, named 1.7.0.jdk, inside Contents/Plugins and:
	
	defaults write com.openendedgroup.Field use16 NO

Finally, to run from the command line, run 

	./Contents/MacOS/field_mac64.sh -field.scratch nameOfFileToOpen.field

### Running --- Linux

To run:

	./Contents/Linux/field_linux32.sh -field.scratch nameOfFileToOpen.field

or:

	./Contents/Linux/field_linux64.sh -field.scratch nameOfFileToOpen.field

Should you find that Field crashes on startup complaining of "No Handles", you need to install libwebkitgtk-1.0. For example:

	sudo apt-get install libwebkitgtk-1.0-0


