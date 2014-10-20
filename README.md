This project never got off the ground, go here:
===============================================

Lightweight bash package manager 
http://bpkg.io/


dpend
=====

A dependency management framework for bash scripts.

Purpose
-------
There is a lot of cool stuff out there written in Bash. [Dotfiles] (http://github.com/dougborg/bashrc), [testing frameworks] (http://github.com/sstephenson/bats), deployment frameworks, etc. Unfortunately, bash doesn't really have a common way to manage bash script dependencies. This leads to people solving the same problems over and over again, or (not much better) copying little snippets of code they found, modifying them to suit thier own purpose and rarely contributing back to the original script. This is great, but it means there is little to no community around bash script development.

The aim of this project is to create that community. Perl has cpan, Python has pip, Ruby has gems, Java has maven central; bash will now have dpend.

Implementation Plan
-------------------
The first stage will be to create a small script that can be used to bootstrap (download and source) the main dpend script. From there, dpend and its conventions will take over downloading and sourcing the necessary dependencies for your scripts.

dpend will also provide a "build" system for bash script modules. This will include convention-over-configuration support for testing, packaging and structuring a .dpend module.

### General design tenets:
  - dpend shall be written primarily for Bash v4; scripts MAY degrade gracefully for Bash v3.
  - dpend shall strive to support Bash installed on as many platforms as possible, but GNU/Linux and OSX will be the primary focus.
  - dpend's main infrastructure will be as Bash-only as possible; external requirements shall be minimized as much as possible.
  - dpend shall establish and encourage best-practice conventions for bash scripts, and bash script packages.

### For version 1.0, dpend will support the sourcing of:
  - github gists
  - local folders (source .sh files recursively)
  - local / remote .sh files
  - local / remote .dpend archives (conforming to a TBD dpend packaging standard w/ resolution of transitive dpendencies.)
  - a dpend standard coordinate system (TBD, but potentially similiar to Gradle's "org:module:version" standard.)

### Version 1.0 will also support:
  - local caching of remote dpend resources.
  - a convention-over-configuration "build" framework for structuring, testing, and publishing dpend packages.
