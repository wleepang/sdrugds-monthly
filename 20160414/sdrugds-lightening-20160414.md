# Deploying Self Contained Desktop Shiny Apps

## Desktop apps in R?
Compared to other data analysis platforms (Python, Matlab, ...) R's main weakness
is the inability to "compile" desktop executables.

Developing R (web)applications is easy with Shiny.
Options for sharing are:

* Publish to a server
* Ship with a package
* Bundle a set of scripts

All of the above require some level of experience with R - i.e. how to run R code and install
R packages.

### Ease of use ...
> Presenting people, especially rank-and-file users, with a command-line
> application is among the fastest ways to reduce its use.

http://slott-softwarearchitect.blogspot.com/2016/04/the-gui-problem.html

## Background
Needed to deploy R/Shiny-based applications to users who:
* have little to no R / programming experience
  * would run away from instructions that start with "open an R console ..."

* work under complete IT-lockdown
  * _cannot_ install software even if they knew how

* work solely in a Windows environment

## Requirements:
* as self-contained as possible
* easy user launch point - i.e. a single file to double click
* runs on the desktop
  * limited (admin) access to a linux server
  * maintaining the stack for a shiny app server can be challenging
  * The free version of shiny-server has concurrency limitations

## Caveats
This system is currently designed for Windows based deployments.
(I needed to do this in a 100% Windows house)
(I didn't have a Mac to test this on)

## Framework
* "Portable" R
  * Users may not have R installed on their workstations
  * Users may not have _the ability to install_ R on their workstations

* Self-contained R application
  * library of dependencies
  * application code (e.g. for Shiny: ui.R, server.R)
  * application configuration files

* OS scripts (javascript / batch)
  * launching the app via simple "double-click this icon"

* [Optional] User space installer

## Demo
Self-contained DFaceR app

## A couple tricks
* Use user profile log files for "shared" applications
* Rscript is better than R CMD BATCH
* Prepare for Shiny termination
* Initially tried Chrome Portable in app-mode, but ...
  * too many weird errors
  * BIG deployments
  * modern-ish browsers work just fine with latest shiny (IE 10+, FF, GC)

## Any R app ...
* Also tested with RGtk based applications
* Really, anything that can be launched with Rscript

## Learn more, Try it, contribute
* Blog post
* Github Repo
