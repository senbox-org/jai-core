# Java Advanced Imaging

This version of Java Advanced Imaging has been modified so it works with OpenJDK too.

To build the JAI packages, you must first checkout this [jai-core](https://github.com/senbox-org/jai-core) 
git repository on [GitHub](https://github.com/). Therefore you can use tools offered by GitHub or the command line.

Step into your projects base directory. E.g. D:\projects \
Then clone the GitGub repository by typing  \
This will create a new directory named `jai-core` in you projects base directory with the followin content:

    D:\>cd projects
    
    D:\projects>git clone https://github.com/senbox-org/jai-core.git
    Cloning into 'jai-core'...
    remote: Enumerating objects: 30, done.
    remote: Counting objects: 100% (30/30), done.
    remote: Compressing objects: 100% (21/21), done.
    remote: Total 2052 (delta 15), reused 20 (delta 9), pack-reused 2022
    Receiving objects: 100% (2052/2052), 100.31 MiB | 27.13 MiB/s, done.
    Resolving deltas: 100% (872/872), done.
    Checking out files: 100% (884/884), done.
    
    D:\projects>cd jai-core
    
    D:\projects\jai-core>dir /a
     Volume in drive D has no label
     Volume Serial Number is F4AC-9851
    
     Directory of D:\projects\jai-core
    
    13.12.2019  09:15    <DIR>          .
    13.12.2019  09:15    <DIR>          ..
    13.12.2019  09:15    <DIR>          .git
    13.12.2019  09:15                79 .gitignore
    13.12.2019  09:15                79 .travis.yml
    13.12.2019  09:15    <DIR>          build-tools
    13.12.2019  09:15             1.616 build.properties
    13.12.2019  09:15            39.774 build.xml
    13.12.2019  09:15             2.530 COPYRIGHT.txt
    13.12.2019  09:15             7.013 LICENSE-jaispec.txt
    13.12.2019  09:15            18.622 LICENSE-JDL.txt
    13.12.2019  09:15             7.255 LICENSE-JRL.txt
    13.12.2019  09:15            10.556 LICENSE-mediaLibJAI.txt
    13.12.2019  09:15               386 LICENSE.txt
    13.12.2019  09:15             3.821 README-build.html
    13.12.2019  09:15             2.591 README.md
    13.12.2019  09:15    <DIR>          src
    13.12.2019  09:15    <DIR>          www
                  12 Datei(en),         94.322 Bytes
                   6 Verzeichnis(se), 409.259.569.152 Bytes frei
    
    D:\projects\jai-core>
 

## System Requirements

Any operating environment that supports OpenJDK version > 7 should work.
We have built `jai-core` on the following operating environments:

* Windows: Windows 10 and [OpenJDK](https://adoptopenjdk.net/) 

The following software must be installed:

* [OpenJDK 8](https://adoptopenjdk.net/) or later.
  It should also work with other OpenJDK providers.   
* [Apache Ant 1.10.5](http://jakarta.apache.org/ant) or later
* [Apache Maven 3.3.1](https://maven.apache.org/) or later

## Building Java Advanced Imaging

Before you start building, your PATH must include the following directories:

* <ant-root-dir>/bin
* <jdk-root-dir>/bin
* Setting JAVA_HOME or JAVACMD environment variable will supersede <jdk-root-dir>/bin for ant.  
  For further details please refer to the ant manual.

The default ant target, `mvn-install-files`, creates both optimized and debug jar files
but only installs the optimized jar to the local maven repository.

To build:

    cd <project-base-dir>/jai-core
    ant

The above steps build both the Java code for `javax.media.jai.*` and `com.sun.media.jai.*` packages.

The build will be placed in `jai-core/build/<platform>/opt`, where `<platform>` is determined from the `ant echo` command:

    ant echo

Jar files are placed in `jai-core/build/<platform>/opt/lib/ext`. Binaries for native libraries are part of the project
and are copied to the `jai-core/build/<platform>/opt/<jrenativesubdir>` directory as part of the build, where 
`<jrenativesubdir>` is determined from the `ant echo` command as above.

To see other targets that are available, type `"ant -projecthelp"`. Note that ant must be run from the top-level directory.

## Running Java Advanced Imaging

To run Java Advanced Imaging, please checkout the [jai-demos](https://jai-demos.dev.java.net/) project and then refer 
to [README-build.html](http://localhost:63342/jai-demos/README-build.html) in jai-demos for details on building and 
running Java Advanced Imaging demo programs.


#### copyrights ... licences

The source code for the jai-core project is copyrighted code that
is licensed to individuals or companies who download or otherwise
access the code.

The copyright notice for this project is in COPYRIGHT.txt

The source code license for this project is in LICENSE.txt
