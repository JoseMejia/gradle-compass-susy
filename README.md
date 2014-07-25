gradle-compass-susy
===================

Gradle tasks for compiling and watching scss files with Jruby, Compass 1.0.0.alpha, and Susy Grid 2.1.3

These tasks will allow you to integrate a sass compile project to your gradle build easily without requiring root permissions
nor dealing with complicated ruby gems and their dependencies.

*gradle-compass-susy* installs a portable out-of-the-box jruby along with the Susy Grid 2 framework (http://susy.oddbird.net/)
to support convenient mixins in your responsive design.

## Gradle tasks ##

The *build.gradle* file comprises three major tasks:
 1. installSass
 2. compileSass
 3. watchSass

The task *installSass* downloads and extracts the jruby 1.7.13 distribution locally and installs the gems necessary for
managing Compass projects.   *compileSass* and *watchSass* correspond to the compass compile and watch commands;
both depend on the task *installSass*, which should run once.

Please remark that *installSass* overwrites the file *.gemrc* on your home directory to enable http://rubygems.org
as source for the gem installation.

## Configuration ##

In *build.gradle*, one can set the path of the compass project and the destination path for jruby.  The default values
are the relative paths:
>compassProject = file("demo")

>jrubyDestination = '.jruby'

The compilation settings take place in the *config.rb* of your compass project as usually.

## Requirements ##
Our tasks have been tested with Gradle 1.9 and JDK 7/8 on Windows 7 and 64 bits Linux.
Do not forget to set the environment variable JAVA_HOME according to your java version.