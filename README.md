# Building the Java Advanced Imaging Packages

To build the Java Advanced Imaging packages, you must first checkout the [jai-core](http://jai-core.dev.java.net/) 
CVS repository on java.net. For example, run the cvs checkout command as follows:

    cd <cvs-root-dir>
    cvs checkout jai-core

## System Requirements

Any operating environment that supports J2SE should work. We have built `jai-core` on the following 
operating environments:

* Solaris-sparc: Sparc (Ultra60 or better) running Solaris 9
* Solaris-x86: i386/i586 running Solaris-x86 9
* Linux: i386/i586 running SuSE 9 or RedHat 9.0
* Windows: Windows/XP, Windows 2000, Windows 7, Windows 10

The following software must be installed:

* [J2SE 1.3](http://java.sun.com/j2se) or later.
* [Apache Ant 1.6](http://jakarta.apache.org/ant) or later

## Building Java Advanced Imaging

Before you start building, your PATH must include the following directories:

* <ant-root-dir>/bin
* <jdk-root-dir>/bin
* Setting JAVA_HOME or JAVACMD environment variable will supersede <jdk-root-dir>/bin for ant.  
  For further details please refer to the ant manual.

The default target, jar, creates both optimized and debug jar files.

To build:

    cd <cvs-root-dir>/jai-core
    ant

The above steps build both the Java code for `javax.media.jai.*` and `com.sun.media.jai.*` packages.

The build will be placed in `jai-core/build/<platform>/opt`, where `<platform>` is determined from the `ant echo` command:

    ant echo

Jar files are placed in `jai-core/build/<platform>/opt/lib/ext`. Binaries for native libraries are part of the project
and are copied to the `jai-core/build/<platform>/opt/<jrenativesubdir>` directory as part of the build, where 
`<jrenativesubdir>` is determined from the `ant echo` command as above.

To see other targets that are available, type `"ant -projecthelp"`. Note that ant must be run from the top-level directory.

##Running Java Advanced Imaging
To run Java Advanced Imaging, please checkout the [jai-demos](https://jai-demos.dev.java.net/) project and then refer 
to [README-build.html](http://localhost:63342/jai-demos/README-build.html) in jai-demos for details on building and 
running Java Advanced Imaging demo programs.


#### copyrights ... licences

The source code for the jai-core project is copyrighted code that
is licensed to individuals or companies who download or otherwise
access the code.

The copyright notice for this project is in COPYRIGHT.txt

The source code license for this project is in LICENSE.txt